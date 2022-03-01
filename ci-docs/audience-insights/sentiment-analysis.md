---
title: Semantisk analyse for tilbakemelding fra kunder
description: Finn ut hvordan du bruker en sentimentanalysemodell på tilbakemelding fra kunder i Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 05e530a1bc96c5fd9c7a3bc0197563d8fe330387
ms.sourcegitcommit: cb71e39de9b891c24bd5cd9c014eb3eeb537ac24
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/10/2022
ms.locfileid: "7951086"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analysere sentiment i tilbakemelding fra kunder (forhåndsversjon)

I dag forventer kunder produkter, tjenester og opplevelser av høy kvalitet. Særlig kunder som gir tilbakemelding. Det er svært utfordrende for organisasjoner å analysere en økende mengde data uten å redusere nøyaktigheten og øke arbeidskostnadene. Dynamics 365 Customer Insights har en sentimentanalysemodell for tilbakemelding fra kunder som gjør at organisasjoner kan analysere dataene mer nøyaktig til en lavere pris.

Sentimentanalyse gjør at du kan syntetisere kundesentiment og identifisere forretningsaspekter som forbedringsmuligheter. Denne funksjonen i Customer Insights hjelper deg å forstå hva som fungerer bra, og hva som må endres. Fokuser på de mest relevante og virkningsfulle forretningsområdene for å forbedre opplevelsen for kundene. Den kan i siste instans hjelpe deg med forretningshandlinger som gir kunder erfaringer som gjør dem mer fornøyde og lojale.

## <a name="overview"></a>Oversikt

Funksjonen for sentimentanalyse genererer to utledede innsikter per kunde-ID. En sentimentpoengsum (−5 til 5) og en liste over aktuelle forretningsaspekter (forretningsområder) er sammen med på å tydeliggjøre tilbakemeldingen fra kundene. 

Denne informasjonen kan hjelpe deg å oppnå følgende resultater: 
- få en oversikt over kundesentimenter overfor et merke eller en organisasjon
- identifisere kunder med negativt sentiment for å fokusere kampanjene og engasjementene og optimalisere for høyere avkastning  
- identifisere forretningsaspekter med problemer som kunder har påpekt  
- segmentere kunder basert på sentiment for å kjøre tilpassede kampanjer med målrettet salg, markedsføring og kundestøtte
- optimalisere forretningsdrift ved å håndtere problemområder eller salgsmuligheter som kunder har nevnt
- gjenkjenne forretningsaspekter som gjør det bra, og belønne fornøyde kunder gjennom lojalitets- og tilbudsprogrammer

For å sikre at du kan ha tillit til resultatene av modellene, gir vi klar informasjon om hvordan modellene tar beslutninger. Du får en liste over ord som påvirket modellenes beslutning om å tilordne en bestemt sentimentpoengsum eller et bestemt forretningsaspekt til tilbakemeldingskommentarer.  

Vi bruker to **modeller for naturlig språkbehandling (NLP)**: Den første tilordner hver tilbakemeldingskommentar til en sentimentpoengsum. Den andre modellen knytter hver tilbakemelding til alle aktuelle forretningsaspekter. Modellene er opplært på offentlige data fra kilder på tvers av sosiale medier, detaljhandelsbransjen, restaurantbransjen, forbrukerprodukter og bilindustrien.    
  
- Forhåndsdefinerte forretningsaspekter som modellen knytter til tilbakemeldingsdata, omfatter følgende:
-   Kontoadministrasjon
-   Utsjekking og betaling
-   Kundestøtte
-   Henting i butikken
-   Pakkelevering og -henting
-   Forhåndsbestilling
-   Pris
-   Personvern og sikkerhet
-   Kampanjer og belønninger
-   Kvittering og garanti
-   Returbytte og annullering
-   Fullføringsnøyaktighet
-   Nettsteds-/appkvalitet

> [!NOTE]
> Vi støtter for øyeblikket bare sentimentanalyse på engelsk tilbakemelding fra kunder. Vi kommer til å støtte flere språk senere. Hvis tilbakemelding på andre språk lastes opp, returnerer modellen likevel resultater. Disse resultatene er imidlertid ikke nøyaktige. 

## <a name="prerequisites"></a>Krav

Sentimentanalyse er basert på teksttilbakemeldingsdata som har gått gjennom [dataforeningsprosessen](data-unification.md). Vi anbefaler på det sterkeste at du [konfigurerer enhetene for tilbakemeldingsdata som aktivitetsenheter av semantisk type](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (tilbakemeldingstype) på forhånd. 

Hvis du vil konfigurere en sentimentanalysemodell, trenger du minst [bidragsytertillatelser](permissions.md).

Customer Insights kan behandle opptil 10 millioner tilbakemeldingsoppføringer i én kjøring av modellen. Modellen kan analysere tilbakemeldingskommentarer på opptil 128 ord. Hvis en tilbakemeldingskommentar er lengre, tar analysen bare hensyn til de første 128 ordene.

### <a name="data-requirements"></a>Datakrav
  
Følgende dataattributter kreves:
- Enhetlig kunde-ID (UCID) for å samsvare oppføringer for teksttilbakemeldingsdata med en enkeltkunde. Denne ID-en er et resultat av [dataforeningsprosessen](data-unification.md).
- Tilbakemeldings-ID
- Tidsstempel for tilbakemelding
- Tilbakemeldingstekst   

> [!TIP]
> Sentimentanalyse krever teksttilbakemelding fra kundene. Det er bare én tilbakemeldingsenhet som kan konfigureres for øyeblikket. Hvis det finnes flere tilbakemeldingsenheter, kan du forene dem i Power Query før datainntak begynner.

## <a name="configure-a-sentiment-analysis"></a>Konfigurere en sentimentanalyse 

1. Gå til **Intelligens** > **Prognoser** i Customer Insights.

1. Velg **Bruk modell** på flisen **Kundesentimentanalyse**.

1. Velg **Kom i gang** i ruten **Kundesentimentanalyse (forhåndsversjon)**.

1. Angi et **Navn** for analysen i trinnet **Modellnavn**. 

1. Angi **Navn på utdataenhet for forretningsaspekt** og **Navn på utdataenhet for sentimentpoengsum**, og velg deretter **Neste**.

1. Velg **Legg til data** i trinnet **Obligatoriske data**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Legg til dataflyt i sentimentanalysemodellen.":::

1. Velg den semantiske typen **Tilbakemelding** fra listen i ruten **Legg til data**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurasjonstrinn for valg av tilbakemeldingsaktiviteter for sentimentanalyse.":::

1. Velg aktivitetene du vil bruke for denne sentimentanalysen, og velg deretter **Neste**.
 
1. Tilordne attributtene i dataene til modellattributtene. Velg **Lagre** for å bruke valgene. 

1. Statusen til datatilordningen vises. Velg **Neste** for å fortsette. 

1. I trinnet **Se gjennom modelldetaljene** validerer du konfigurasjonen av sentimentanalysen. Du kan gå tilbake til enhver del av prediksjonskonfigurasjonen. Velg **Lagre og kjør** for å starte analysen. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Gjennomgangstrinn for sentimentmodellen der alle konfigurerte elementer vises.":::

1. Velg **Ferdig** for å gå ut av konfigurasjonen. Det kan ta flere timer å fullføre prosessen, avhengig av datamengden som brukes. 

## <a name="review-analysis-status"></a>Se gjennom analysestatusen

1.  Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.
2.  Velg prognosen du vil gå gjennom.
- **Navn på prediksjon**: Navnet på prediksjonen som ble angitt under opprettingen.
- **Prediksjonstype**: Typen modell som brukes for prediksjonen.
- **Utdataenhet**: Navn på enheten for å lagre utdataene fra prediksjonen. Gå til **Data** > **Enheter** for å finne enheten med dette navnet.
- **Forespeilet felt**: Dette feltet fylles bare ut for enkelte typer prediksjoner, og brukes ikke i predisjon av verdi for kundelevetid.
- **Status**: Statusen for prediksjonskjøringen.
  - **I kø**: Prediksjonen venter på at andre prosesser skal fullføres.
  - **Oppdaterer**: Prediksjonen kjører for å opprette resultater som flytes til utdataenheten.
  - **Mislyktes**: Prediksjonskjøringen mislyktes. Se gjennom loggene for mer informasjon.
  - **Fullført**: Prediksjonen ble fullført. Velg Vis under de loddrette ellipsene for å se gjennom prediksjonsresultatene.
- **Redigert**: Datoen da konfigurasjonen av prediksjonen ble endret.
- **Sist oppdatert**: Datoen prediksjonen hadde oppdaterte resultater i utdataenheten.

## <a name="manage-sentiment-analysis"></a>Administrer sentimentanalyse

Du kan optimalisere, feilsøke, oppdatere eller slette prediksjoner. Se gjennom en brukbarhetsrapport for inndata for å finne ut hvordan du gjør en prediksjon raskere og mer pålitelig. Hvis du vil ha mer informasjon, kan du se [Administrere prediksjoner](manage-predictions.md).

## <a name="review-analysis-results"></a>Se gjennom analyseresultater
 
1. Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**. 
1. Velg navnet på prediksjonen du vil se gjennom resultater for. I dette tilfellet velger du sentimentanalysen du vil se gjennom. 

### <a name="summary-tab"></a>Sammendrag-kategori

Det er fire hoveddeler med data på resultatsiden. 

- **Gjennomsnittlig sentimentpoengsum**: Hjelper deg å forstå det generelle sentimentet for alle kunder. Sentimentpoengsummene er gruppert i tre kategorier: 
  1.    Negativt (−5 > 2)
  2.    Nøytralt (−1 > 1)
  3.    Positivt (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Visuell representasjon av det generelle kundesentimentet.":::

- **Distribusjon av kunder etter sentimentpoengsum**: Kunder kategoriseres i negative, nøytrale og positive grupper basert på sentimentpoengsummene. Hold musepekeren over stolpene i histogrammet for å vise antall kunder og gjennomsnittlig sentimentpoengsum i hver gruppe. Disse dataene kan hjelpe deg å [opprette kundesegmenter](segments.md) basert på sentimentpoengsummene deres.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Stolpediagram som viser kundesentimentet på tvers av de tre sentimentgruppene.":::

- **Gjennomsnittlig sentimentpoengsum over tid**: Kundesentimentet kan endres over tid. Vi viser trender i kundenes sentimenter i tidsrommet dataene dine er i. Denne visningen kan hjelpe deg å måle virkningen av sesongbaserte kampanjer, produktlanseringer eller andre tidsbundne inngrep i kundesentimentet. Se diagrammet ved å velge interesseåret på rullegardinmenyen. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Historikkdiagram med sentimentpoengsummen over tid representert som en linje.":::
 
- **Sentiment på tvers av forretningsaspekter**: Denne tabellen viser gjennomsnittlig sentiment på tvers av forretningsaspekter. Den kan hjelpe deg å måle hvilke aspekter ved virksomheten som kundene allerede er fornøyde med, eller aspekter som krever mer oppmerksomhet. Tilbakemeldingsoppføringer som ikke passer under noen av de støttede forretningsaspektene, kategoriseres under **Andre**. Tabellen sorteres som standard alfabetisk. Du kan endre sorteringen ved å velge en tabelloverskrift.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Liste over forretningsaspekter med den tilknyttede sentimentverdien og antall kunder som nevner den.":::
 
  Velg navnet på et forretningsaspekt for å vise mer informasjon om hvordan det identifiseres av modellen. Det er to deler i denne ruten: 

  - **Innflytelsesrike ord**: Viser de mest populære ordene som påvirket identifiseringen til modellen for kunstig intelligens av et forretningsaspekt i tilbakemelding fra kunder. 
    **Vis støtende ord**: Lar deg ta med støtende ord fra de opprinnelige tilbakemeldingsdataene fra kundene, i listen. Dette er som standard deaktivert.  Maskering av støtende ord er basert på en modell for kunstig intelligens, og alle støtende ord blir kanskje ikke oppdaget. Vi fortsetter å gjenta og lære opp klassifisereren for å oppnå best mulig ytelse. Hvis du oppdager et støtende ord som ikke ble filtrert som forventet, gir du oss beskjed. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Liste over innflytelsesrike ord med veksleknapp for å vise eller skjule støtende ord.":::
 
  - **Tilbakemeldingseksempler:** Viser faktiske tilbakemeldingsoppføringer i dataene. Ordene fargekodes i henhold til hvordan de påvirker identifiseringen av et forretningsaspekt. 


### <a name="influential-words-analysis-tab"></a>Analysefanen Innflytelsesrike ord

Det er tre deler med mer informasjon som forklarer hvordan sentimentmodellen fungerer.
  
1. **Populære ord som bidrar til positivt sentiment**: Viser de mest populære ordene som påvirket identifiseringen til modellen for kunstig intelligens av positivt sentiment i tilbakemelding fra kunder.  
2. **Populære ord som bidrar til negativt sentiment**: Viser de mest populære ordene som påvirket identifiseringen til modellen for kunstig intelligens av negativt sentiment i tilbakemelding fra kunder.  
3. **Tilbakemeldingseksempler**: Viser faktiske tilbakemeldingsoppføringer, én med et negativt sentiment og én med et positivt sentiment. Ord i tilbakemeldingsoppføringene utheves i henhold til bidraget deres til den tilordnede sentimentpoengsummen. Ord som bidrar til en positiv sentimentpoengsum, utheves i grønt. Ord som bidrar til en negativ poengsum, utheves i rødt.
   Velg **Vis mer** hvis du vil laste inn flere tilbakemeldingseksempler som gir mer informasjon om og kontekst til hvordan sentimentmodellen fungerer.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Eksempler på sentimentanalyse på tilbakemelding fra kunder.":::
 
**Vis støtende ord**: Lar deg ta med støtende ord fra de opprinnelige tilbakemeldingsdataene fra kundene, i listen. Dette er som standard deaktivert.  Maskering av støtende ord er basert på en modell for kunstig intelligens, og alle støtende ord blir kanskje ikke oppdaget. Vi fortsetter å gjenta og lære opp klassifisereren for å oppnå best mulig ytelse. Hvis du oppdager et støtende ord som ikke ble filtrert som forventet, gir du oss beskjed. 

## <a name="act-on-analysis-results"></a>Handle basert på analyseresultater

Du kan enkelt begynne å opprette nye kundesegmenter fra resultatsiden for sentimentanalyse ved å velge **Opprett segmenter** øverst på resultatsiden for modellen.

:::image type="content" source="media/create-segment-model.png" alt-text="Kommandolinje med alternativer for prediksjonsmodeller.":::
 
## <a name="potential-bias"></a>Mulig skjevhet

Du må være oppmerksom på mulig skjevhet i dataene du bruker til å forutsi kundesentiment, som med alle funksjoner som bruker prediktiv kunstig intelligens. Hvis du for eksempel bare samler inn tilbakemelding digitalt, kan du gå glipp av tilbakemelding fra kunder som hovedsakelig gjør forretninger med deg personlig, og dette kan påvirke resultatet av funksjonen.

Siden denne funksjonen bruker automatiserte metoder til å evaluere data og lage prediksjoner basert på disse dataene, kan den derfor brukes som en metode for profilering, slik denne termen er definert i EUs personvernforordning (GDPR). Din bruk av denne funksjonen til å behandle data kan være underlagt GDPR eller andre lover eller forskrifter. Du har ansvaret for å sikre at bruken din av Dynamics 365 Customer Insights, inkludert sentimentanalyse, er i samsvar med alle gjeldende lover og forskrifter, inkludert lover knyttet til personvern, personopplysninger, biometriske data, databeskyttelse og konfidensialitet i kommunikasjon.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

