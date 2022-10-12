---
title: Analyser sentiment for kundetilbakemelding (forhåndsversjon)
description: Finn ut hvordan du bruker en sentimentanalysemodell på tilbakemelding fra kunder i Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610478"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analyser sentiment i tilbakemelding fra kunder (forhåndsversjon)

Sentimentanalyse gjør at du kan syntetisere kundesentiment og identifisere forretningsaspekter som forbedringsmuligheter. Denne funksjonen i Customer Insights hjelper deg å forstå hva som fungerer bra, og hva som må endres. Den kan deg med forretningshandlinger som gir kunder opplevelser som gjør dem mer fornøyde og lojale.

## <a name="overview"></a>Oversikt

Funksjonen for sentimentanalyse genererer to utledede innsikter per kunde-ID. En sentimentpoengsum (fra -5 til 5) og en liste over aktuelle forretningsaspekter (forretningsområder) som sammen bidrar til å tydeliggjøre tilbakemeldingen fra kundene.

Denne analysen hjelper deg med følgende:
- få en oversikt over kundesentimenter overfor et merke eller en organisasjon
- identifisere kunder med negativt sentiment for å fokusere kampanjene og engasjementene og optimalisere for høyere avkastning  
- identifisere forretningsaspekter med problemer som kunder har påpekt  
- segmentere kunder basert på sentiment for å kjøre tilpassede kampanjer med målrettet salg, markedsføring og kundestøtte
- optimalisere forretningsdrift ved å håndtere problemområder eller salgsmuligheter som kunder har nevnt
- gjenkjenne forretningsaspekter som gjør det bra, og belønne fornøyde kunder gjennom lojalitets- og tilbudsprogrammer

Modellen inneholder en liste over ord som påvirket modellens beslutning om å tilordne en bestemt sentimentpoengsum eller et bestemt forretningsaspekt til tilbakemeldingskommentarer.  

Vi bruker to **modeller for naturlig språkbehandling (NLP)**: Den første tilordner hver tilbakemeldingskommentar til en sentimentpoengsum. Den andre modellen knytter hver tilbakemelding til alle aktuelle forretningsaspekter. Modellene er opplært på offentlige data fra kilder på tvers av sosiale medier, detaljhandelsbransjen, restaurantbransjen, forbrukerprodukter og bilindustrien.
  
Forhåndsdefinerte forretningsaspekter som modellen knytter til tilbakemeldingsdata, omfatter følgende:
- Kontoadministrasjon
- Utsjekking og betaling
- Kundestøtte
- Henting i butikken
- Pakkelevering og -henting
- Forhåndsbestilling
- Pris
- Personvern og sikkerhet
- Kampanjer og belønninger
- Kvittering og garanti
- Returbytte og annullering
- Fullføringsnøyaktighet
- Nettsteds-/appkvalitet

> [!NOTE]
> Vi støtter for øyeblikket bare sentimentanalyse på engelsk tilbakemelding fra kunder. Vi kommer til å støtte flere språk senere. Hvis tilbakemelding på andre språk lastes opp, returnerer modellen likevel resultater. Disse resultatene er imidlertid ikke nøyaktige.

## <a name="prerequisites"></a>Forutsetning

- Minst [Bidragsyter-tillatelser](permissions.md)
- [Enhetlig](data-unification.md) teksttilbakemeldingsdata. Vi anbefaler på det sterkeste at du [konfigurerer enhetene for tilbakemeldingsdata som aktivitetsenheter av semantisk type](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (tilbakemeldingstype).
- Enhetlig kunde-ID (UCID) fra datasamling for å samsvare oppføringer for teksttilbakemeldingsdata med en enkeltkunde.
- Tilbakemeldings-ID
- Tidsstempel for tilbakemelding
- Tilbakemeldingstekst

Customer Insights kan behandle opptil 10 millioner tilbakemeldingsoppføringer i én kjøring av modellen. Modellen kan analysere tilbakemeldingskommentarer på opptil 128 ord. Hvis en tilbakemeldingskommentar er lengre, tar analysen bare hensyn til de første 128 ordene.

> [!NOTE]
> Det er bare én tilbakemeldingsenhet som kan konfigureres. Hvis det finnes flere tilbakemeldingsenheter, kan du kombinere dem i Power Query før datainntak begynner.

## <a name="configure-a-sentiment-analysis"></a>Konfigurere en sentimentanalyse

1. Gå til **Intelligens** > **Prediksjoner**.

1. Velg **Bruk modell** på flisen **Kundesentimentanalyse (forhåndsversjon)** i **Opprett**-fanen.

1. Velg **Komme i gang**.

1. Gi analysen et **Navn**, og oppgi **Navn på utdataenhet for forretningsaspekt** og **Navn på utdataenhet for sentimentpoengsum**.

1. Velg **Neste**.

1. Velg **Legg til data** for **Kundetilbakemelding**.

1. Velg den semantiske aktivitetstypen **Tilbakemelding** som inneholder tilbakemeldingsdataene. Hvis aktiviteten ikke er konfigurert, velger du **her** og oppretter den.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurasjonstrinn for valg av tilbakemeldingsaktiviteter for sentimentanalyse.":::

1. Velg aktivitetene du vil bruke for denne sentimentanalysen, og velg deretter **Neste**.

1. Tilordne attributtene i dataene til modellattributtene. 

1. Velg **Lagre**.

1. Velg **Neste**. Trinnet **Se gjennom og kjør** viser et sammendrag av konfigurasjonen og lar deg gjøre endringer før du oppretter analysen.

1. Velg **Rediger** i et av trinnene for å se gjennom og gjøre endringer.

1. Hvis du er fornøyd med valgene, velger du **Lagre og kjør** for å begynne å kjøre modellen. Velg **Ferdig**. Fanen **Mine prediksjoner** vises mens prediksjon opprettes. Det kan ta flere timer før prosessen er fullført, avhengig av mengden data som brukes i forutsigelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Vis analyseresultater

1. Gå til **Intelligens** > **Prediksjoner**.

1. I fanen **Mine prediksjoner** velger du prediksjonen du vil vise.

Det finnes to faner med resultater.

### <a name="sumary-tab"></a>Sammendrag-fanen

Det er fire hoveddeler med data på resultatsiden.

- **Gjennomsnittlig sentimentpoengsum**: Sentimentpoengsummer hjelper deg å forstå det generelle sentimentet for alle kunder.
  - **Negativ** (-5 > 2)
  - **Nøytral** (-1 > 1)
  - **Positiv** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Visuell representasjon av det generelle kundesentimentet.":::

- **Distribusjon av kunder etter sentimentpoengsum**: Kunder kategoriseres i negative, nøytrale og positive grupper basert på sentimentpoengsummene. Hold musepekeren over stolpene i histogrammet for å vise antall kunder og gjennomsnittlig sentimentpoengsum i hver gruppe. Disse dataene kan hjelpe deg å [opprette kundesegmenter](prediction-based-segment.md) basert på sentimentpoengsummene deres.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Stolpediagram som viser kundesentimentet på tvers av de tre sentimentgruppene.":::

- **Gjennomsnittlig sentimentpoengsum over tid**: Kundesentimentet kan endres over tid. Vi viser trender i kundenes sentimenter i tidsrommet dataene dine er i. Denne visningen hjelper deg å måle virkningen av sesongbaserte kampanjer, produktlanseringer eller andre tidsbundne inngrep i kundesentimentet. Se diagrammet ved å velge interesseåret på rullegardinmenyen.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Historikkdiagram med sentimentpoengsummen over tid representert som en linje.":::

- **Sentiment på tvers av forretningsaspekter**: Gjennomsnittlig sentiment på tvers av forretningsaspekter hjelper deg å finne ut hvilke aspekter ved virksomheten kunder allerede er fornøyd med, eller som krever mer oppmerksomhet. Tilbakemeldingsoppføringer som ikke passer under noen av de støttede forretningsaspektene, kategoriseres under **Andre**. Sorter dataene ved å velge en kolonne.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Liste over forretningsaspekter med den tilknyttede sentimentverdien og antall kunder som nevner den.":::

  Velg navnet på et forretningsaspekt for å se hvordan det identifiseres av modellen:

  - **Innflytelsesrike ord**: De mest populære ordene som påvirket identifiseringen til modellen for kunstig intelligens av et forretningsaspekt i tilbakemelding fra kunder.
    **Vis støtende ord**: Lar deg ta med støtende ord fra de opprinnelige tilbakemeldingsdataene fra kundene, i listen. Dette er som standard deaktivert.  Maskering av støtende ord er basert på en modell for kunstig intelligens, og alle støtende ord blir kanskje ikke oppdaget. Hvis du oppdager et støtende ord som ikke ble filtrert som forventet, gir du oss beskjed.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Liste over innflytelsesrike ord med veksleknapp for å vise eller skjule støtende ord.":::

  - **Tilbakemeldingseksempler**: Faktiske tilbakemeldingsoppføringer i dataene. Ordene fargekodes i henhold til hvordan de påvirker identifiseringen av et forretningsaspekt.

### <a name="influential-words-analysis-tab"></a>Analysefanen Innflytelsesrike ord

Det er tre deler med mer informasjon som forklarer hvordan sentimentmodellen fungerer.
  
- **Populære ord som bidrar til positivt sentiment**: De mest populære ordene som påvirket identifiseringen til modellen for kunstig intelligens av positivt sentiment i tilbakemelding fra kunder.  

- **Populære ord som bidrar til negativt sentiment**: De mest populære ordene som påvirket identifiseringen til modellen for kunstig intelligens av negativt sentiment i tilbakemelding fra kunder.

- **Tilbakemeldingseksempler**: Faktiske tilbakemeldingsoppføringer, én med et negativt sentiment og én med et positivt sentiment. Ord i tilbakemeldingsoppføringene utheves i henhold til bidraget deres til den tilordnede sentimentpoengsummen. Ord som bidrar til en positiv sentimentpoengsum, utheves i grønt. Ord som bidrar til en negativ poengsum, utheves i rødt.
   Velg **Vis mer** for å laste inn flere tilbakemeldingseksempler.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Eksempler på sentimentanalyse på tilbakemelding fra kunder.":::

**Vis støtende ord**: Lar deg ta med støtende ord fra de opprinnelige tilbakemeldingsdataene fra kundene, i listen. Dette er som standard deaktivert.  Maskering av støtende ord er basert på en modell for kunstig intelligens, og alle støtende ord blir kanskje ikke oppdaget. Hvis du oppdager et støtende ord som ikke ble filtrert som forventet, gir du oss beskjed.

## <a name="act-on-analysis-results"></a>Handle basert på analyseresultater

For å opprette nye kundesegmenter fra resultatsiden for sentimentanalyse velger du **Opprett segmenter** øverst på resultatsiden for modellen.

## <a name="potential-bias"></a>Mulig skjevhet

Det kan finnes mulig skjevhet i dataene du bruker til å forutsi kundesentiment, som i alle funksjoner som bruker prediktiv kunstig intelligens. Hvis du for eksempel bare samler inn tilbakemelding digitalt, kan du gå glipp av tilbakemelding fra kunder som hovedsakelig gjør forretninger med deg personlig, og påvirker resultatet av funksjonen.

Siden denne funksjonen bruker automatiserte metoder til å evaluere data og lage prediksjoner basert på disse dataene, kan den derfor brukes som en metode for profilering, slik denne termen er definert i EUs personvernforordning (GDPR). Din bruk av denne funksjonen til å behandle data kan være underlagt GDPR eller andre lover eller forskrifter. Du har ansvaret for å sikre at bruken din av Dynamics 365 Customer Insights, inkludert sentimentanalyse, er i samsvar med alle gjeldende lover og forskrifter, inkludert lover knyttet til personvern, personopplysninger, biometriske data, databeskyttelse og konfidensialitet i kommunikasjon.

[!INCLUDE [footer-include](includes/footer-banner.md)]

