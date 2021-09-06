---
title: Eksperimenter i Machine Learning Studio (klassisk)
description: Bruk Machine Learning Studio (klassisk)-baserte modeller i Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b979dd177b7c6de1971c02a69748006d041e4d2c3e49a3639dba03212bd7acf9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033735"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Bruke modeller basert på Azure Machine Learning Studio (klassisk)

De ensartede dataene i Dynamics 365 Customer Insights er en kilde for bygging av maskinlæringsmodeller som kan generere ytterligere forretningsinnsikt. Customer Insights integreres med Machine Learning Studio (klassisk), slik at du kan bruke dine egne, tilpassede modeller. Hvis du vil se hvordan modeller som er utviklet i Azure Machine Learning, integreres med Customer Insights, kan du se [Eksperimenter i Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Forutsetninger

- Tilgang til Customer Insights
- Aktivt abonnement på Azure Enterprise
- [Enhetlige kundeprofiler](data-unification.md)
- [Enhetseksport til Azure Blob Storage](export-azure-blob-storage.md) – konfigurasjon

## <a name="set-up-machine-learning-studio-classic"></a>Konfigurere Machine Learning Studio (klassisk)

I det første trinnet må vi opprette et arbeidsområde for og åpne Machine Learning Studio (klassisk).

1. Gå til [https://www.portal.azure.com](https://www.portal.azure.com/) og logg på.

1. Velg **Opprett en ressurs**.

1. Søk etter **Machine Learning Studio-arbeidsområde**, og velg **Opprett**.

1. Angi de nødvendige detaljene for å [opprette arbeidsområdet](/azure/machine-learning/studio/create-workspace). Velg **prisnivået for webtjenesteplanen** basert på datamengden du planlegger å importere. For å få best mulig ytelse bør du velge **stedet** som er nærmest deg geografisk.

1. Når du har opprettet ressursen, vises instrumentbordet for Machine Learning Studio-arbeidsområdet. Velg **Start Machine Learning Studio**.

   ![Brukergrensesnittet i Azure Machine Learning Studio.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Arbeide med Azure Machine Learning Studio

Du kan nå opprette et nytt eksperiment eller importere en eksisterende eksperimentmal fra eksempelgalleriet. Det finnes eksempeleksperimenter for tre standardscenarioer:

- [Frafallsprediksjon](#churn-analysis)

- [Verdi for kundelevetid](#customer-lifetime-value-prediction)

- [Produktanbefaling eller neste beste handling](#productrecommendation-or-next-best-action)

1. Hvis du oppretter et nytt eksperiment eller bruker en eksperimentmal fra galleriet, må du konfigurere egenskapene for **Importer data**. Bruk den veiledede opplevelsen eller legg inn detaljer direkte for å få tilgang til Azure Blob Storage som inneholder dataene dine.  

   ![Azure Machine Learning Studio-eksperiment.](media/azure-machine-learning-studio-experiment.png)

1. Nå kan du bygge en egendefinert behandlingspipeline for å rense og forhåndsbehandle dataene, trekke ut funksjoner og lære opp en passende modell.

1. Test og optimaliser modellytelsen.

1. Når du er fornøyd med kvaliteten på en modell, velger du **Konfigurer nettjeneste** > **Prediktiv nettjeneste**. Dette alternativet importerer den opplærte modellen og pipelinen for funksjonisering fra opplæringseksperimentet til en prediktiv tjeneste. Den prediktive tjenesten kan ta imot et annet sett med inndata med skjemaet som brukes i opplæringseksperimentet, til å lage prediksjoner.

   ![Konfigurer en prediktiv nettjeneste.](media/predictive-webservice-control.png)

1. Når det prediktive nettjenesteeksperimentet er vellykket, kan du distribuere det for automatisk planlegging. Hvis du vil at nettjenesten skal fungere med Customer Insights, velger du **Distribuer nettjeneste** > **Distribuer nettjeneste [Ny] – forhåndsversjon**. [Finn ut mer om hvordan du distribuerer en nettjeneste](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Distribuer en prediktiv nettjeneste.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Eksempelmodeller fra galleriet

Vi bruker et fiktivt scenario av Contoso Hotel for modellene i denne artikkelen. Contoso Hotel samler inn følgende data:

- CRM-data som består av aktivitet under hotelloppholdet. Datasettet inneholder informasjon om oppholdsdatoene for hver registrerte kunde. Det inneholder også informasjon om bestilling, romtyper, utgiftsdetaljer og så videre. Dataene strekker seg over fire år fra januar 2014 til januar 2018.
- Kundeprofiler for hotellgjester. Disse profilene inneholder informasjon om hver kunde, inkludert navn, fødselsdato, postadresse, kjønn og telefonnummer.
- Bruk av tjenester som tilbys av hotellet, for eksempel spa, vaskeri, WiFi eller ilbud. Denne informasjonen blir logget for hver registrerte kunde. Vanligvis er bruk av tjenester koblet til oppholdet. I noen tilfeller kan tjenester brukes av kunder uten å oppholde seg på hotellet.

## <a name="churn-analysis"></a>Frafallsanalyse

Frafallsanalyse brukes på ulike forretningsområder. I dette eksemplet skal vi se på tjenestefrafall, særlig i forbindelse med hotelltjenester som beskrevet ovenfor. Den gir et aktuelt eksempel på en modellpipeline fra ende til ende som kan brukes som utgangspunkt for alle andre typer frafallsmodell.

### <a name="definition-of-churn"></a>Definisjon av frafall

Definisjonen av frafall kan variere etter scenario. I dette eksemplet skal en gjest som ikke har besøkt hotellet i løpet av det siste året, merkes som frafalt.  

Eksperimentmalen kan importeres fra galleriet. Sørg først for at du importerer dataene for **Aktivitet under hotellopphold**, **Kundedata** og **Tjenestebruksdata** fra Azure Blob Storage.

   ![Importer data for frafallsmodellen.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Funksjonisering

Basert på definisjonen av frafall identifiserer vi først råfunksjonene som påvirker etiketten. Deretter konverterer vi disse råfunksjonene til numeriske funksjoner som kan brukes med maskinlæringsmodeller. Dataintegrering skjer i Customer Insights, så vi kan føye sammen disse tabellene ved hjelp av *kunde-ID-en*.

   ![Føy sammen importerte data.](media/join-imported-data.png)

Funksjoniseringen for å bygge modellen for frafallsanalyse kan være litt vanskelig. Dataene er en funksjon av tid med registrering av ny hotellaktivitet daglig. Under funksjonisering ønsker vi å generere statiske funksjoner fra de dynamiske dataene. I dette tilfellet genererer vi flere funksjoner fra hotellaktivitet med et glidevindu på ett år. Vi utvider også de kategoriske funksjonene, for eksempel romtype eller bestillingstype, til separate funksjoner ved hjelp av one-hot-koding.  

Endelig liste over funksjoner:

| **Antall**  | **Original_Column**          | **Avledede funksjoner**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Romtype                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Bestillingstype                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Reisekategori              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Dollar brukt                | TotalDollarSpent                                                                                                                          |
| 5           | Innsjekkings- og utsjekkingsdato  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Tjenestebruk                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Valg av modell

Nå må vi velge den optimale algoritmen som skal brukes. I dette tilfellet er de fleste funksjonene basert på kategoriske funksjoner. Modeller basert på beslutningstre fungerer vanligvis godt. Hvis det bare finnes numeriske funksjoner, kan nevrale nettverk være et bedre valg. Støttevektormaskin (SVM) er også en god kandidat i slike situasjoner. Den må imidlertid justeres en god del for å oppnå den beste ytelsen. Vi velger **Forsterket beslutningstre med to klasser** som første modell, etterfulgt av **SVM med to klasser** som andre modell. Med Azure Machine Learning Studio kan du foreta A/B-testing, så det er fordelaktig å starte med to modeller i stedet for én.

Følgende bilde viser modellopplæringen og evalueringspipelinen fra Azure Machine Learning Studio:

![Frafallsmodell i Azure Machine Learning Studio.](media/azure-machine-learning-model.png)

Vi bruker også en teknikk kalt **Funksjonsviktighet ved permutasjon**, et viktig aspekt ved modelloptimalisering. Innebygde modeller har liten til ingen innsikt i virkningen av en bestemt funksjon på den endelige prediksjonen. Kalkulatoren for funksjonsviktighet bruker en egendefinert algoritme til å beregne innvirkningen til enkeltfunksjoner på resultatet for en bestemt modell. Funksjonsviktigheten normaliseres mellom +1 og -1. En negativ innvirkning betyr at den tilsvarende funksjonen har en kontraintuitiv innvirkning på resultatet, og bør fjernes fra modellen. En positiv innvirkning indikerer at funksjonen bidrar kraftig i retning av prediksjonen. Disse verdiene er ikke korrelasjonskoeffisienter siden de er ulike måledata. Hvis du vil ha mer informasjon, kan du se[Funksjonsviktighet ved permutasjon](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Hele [frafallseksperimentet er tilgjengelig i Azure AI-galleriet](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Prediksjon av verdi for kundelevetid

Beregningen av verdi for kundelevetid er en av de viktigste målingene et selskap kan bruke til å vurdere og segmentere kunder. Det er avgjørende for hotellvirksomheter at de kjenner kundene sine. Det kan for eksempel være avgjørende å forstå hvilke faktorer som utgjør gode kunder. Det hjelper hotelledelsen å vurdere hvilke funksjoner de må fokusere på og forbedre for å gjøre de beste kundene fornøyde. Disse beslutningene kan ha direkte innvirkning på salg og inntekter.  

### <a name="definition-of-cltv"></a>Definisjon av verdi for kundelevetid

I dette eksemplet definerer vi verdi for kundelevetid for en kunde som det totale dollarbeløpet kunden forventes å bruke i løpet av de neste 365 dagene. Vi bruker data fra de siste tre årene for alle kunder til å forutsi denne verdien.

### <a name="featurization"></a>Funksjonisering

I dette tilfellet kommer funksjonisering til å bli svært likt frafallsscenarioet. Etikettene og de forutsagte verdiene er imidlertid forskjellige fra de som er definert ovenfor.

### <a name="model-selection"></a>Valg av modell

Forutsigelse av verdien for kundelevetid er et regresjonsproblem siden den forutsagte verdien er en kontinuerlig variabel med positiv verdi. Basert på funksjonsegenskapene velger vi **Forsterket beslutningstreregresjon** som én algoritme og **Nevralnettverksregresjon** som en annen algoritme for å lære opp modellen.

## <a name="product-recommendation-or-next-best-action"></a>Produktanbefaling eller neste beste handling

Produktanbefaling i et hotellscenario tolkes som å anbefale tjenester som tilbys av hotellet, til kundene. Målet er å velge de riktige tjenestene for kundene slik at bruken av dem maksimeres. Det ligner på filmanbefalinger for brukere av videostrømmingstjenester.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definisjon av produktanbefaling eller neste beste handling

Vi definerer målet som å maksimere dollarbeløpet på bruk av tjenester ved å tilby tjenestene som samsvarer best, til hotellkunder i henhold til interessene deres.

### <a name="featurization"></a>Funksjonisering

På samme måte som med frafallsmodellen føyer vi til hotellets ServiceCustomerID sammen med CustomerID for å lage anbefalinger konsekvent per CustomerID.

![Funksjonisering av anbefalingsmodellen.](media/azure-machine-learning-model-featurization.png)

Dataene stammer fra tre ulike enheter, og funksjoner utledes fra dem. Funksjoniseringen for anbefalingsproblemet er annerledes i forhold til scenarioene med frafall eller verdi for kundelevetid. Anbefalingsmodellen trenger inndata i form av tre sett med funksjoner.

### <a name="model-selection"></a>Valg av modell

Vi forutsier produkter eller tjenester ved å bruke algoritmen kalt **Lær opp Matchbox-anbefaler** til å lære opp anbefalingsmodellen.

![Algoritme for produktanbefaling.](media/azure-machine-learning-model-recommendation-algorithm.png)

De tre inndataportene for modellen **Lær opp Matchbox-anbefaler** tar imot opplæringsdataene for tjenestebruk, kundebeskrivelse (valgfri) og tjenestebeskrivelse. Det er tre forskjellige måter å beregne poeng for modellen på. Den ene måten er for modellevaluering der en NDCG-poengsum (Normalized Discounted Cumulative Gain) beregnes for å rangere de vurderte elementene. I dette eksperimentet har vi NDCG-poengsummen 0,97. De to andre alternativene er å poengberegne modellen for hele tjenestekatalogen som anbefales, eller bare poengberegne elementer som brukere ikke har brukt før.

Hvis vi ser nærmere på distribusjonen av anbefalingene for hele tjenestekatalogen, ser vi at telefon, WiFi og ilbud er de beste tjenestene som anbefales. Dette samsvarer med det vi fant for distribusjonene av tjenesteforbruksdataene:

![Utdata fra anbefalingsmodell.](media/azure-machine-learning-model-output.png)

Du får tilgang til hele [produktanbefalingseksperimentet i Azure AI-galleriet.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrere egendefinerte modeller

Hvis du vil bruke disse prediksjonene i Customer Insights, må du **eksportere** prediksjonene sammen med kunde-ID-ene. [Eksporter dem til samme Azure Blob Storage-plassering](/azure/storage/common/storage-import-export-data-from-blobs) som du eksporterer kildedataene til. Den prediktive nettjenesten kan planlegges til å kjøre regelmessig og oppdatere poengsummene.

Data som genereres av den egendefinerte modellen, kan brukes til å supplere kundedataene ytterligere. Hvis du vil ha mer informasjon, kan du se [Egendefinerte maskinlæringsmodeller](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]