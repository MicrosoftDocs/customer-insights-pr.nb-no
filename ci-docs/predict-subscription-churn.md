---
title: Forutsi abonnementsfrafall (inneholder video)
description: Du kan forutsi om en kunde er i faresonen for ikke lenger å bruke selskapets abonnementsprodukter eller tjenester.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610248"
---
# <a name="predict-subscription-churn"></a>Forutsi abonnementsfrafall

Du kan forutsi om en kunde er i faresonen for ikke lenger å bruke selskapets abonnementsprodukter eller tjenester. Abonnementsdata inkluderer aktive og inaktive abonnementer for hver kunde, slik at det er flere oppføringer per kunde-ID.

Du må ha forretningskunnskap for å forstå hva frafall betyr for bedriften din. Vi støtter tidsbaserte frafallsdefinisjoner, noe som betyr at en kunde anses å ha frafalt et tidsrom etter at abonnementet er avsluttet.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Prøv prediksjon av abonnementsfrafall ved hjelp av eksempeldata: [Eksempelveiledning for prediksjon av abonnementsfrafall](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Forutsetning

- Minst [bidragsytertillatelser](permissions.md).
- Minst 10 kundeprofiler, helst flere enn 1 000 unike kunder.
- Kundeidentifikator, en unik identifikator for å samsvare abonnementer med kundene.
- Abonnementsdata for minst det dobbelte av det valgte tidsvinduet. Fortrinnsvis to til tre år med abonnementsdata. Abonnementsloggen må inneholde følgende:
  - **Abonnements-ID:** Unik identifikator for et abonnement.
  - **Sluttdato for abonnement:** Dato da abonnementet utløper for kunden.
  - **Startdato for abonnement:** Dato når abonnementet starter for kunden.
  - **Transaksjonsdato:** Dato da en abonnementsendring skjedde. For eksempel en kunde som kjøper eller annullerer et abonnement.
  - **Er det et gjentakende abonnement:** Boolsk true/false-felt som avgjør om abonnementet skal fornyes med samme abonnements-ID uten kunde innblanding
  - **Regelmessighetshyppighet (i måneder):** For gjentakende abonnementer er det måneden abonnementet fornyes. Et årlig abonnement som automatisk fornyer for en kunde hvert år for et nytt år, har for eksempel verdien 12.
  - **Abonnementsbeløp**: Valutabeløpet en kunde betaler for fornyelse av abonnementet. Den kan hjelpe deg med å identifisere mønstre for forskjellige abonnementsnivåer.
- Minst to aktivitetsoppføringer for 50 % av kundene du vil beregne frafall for. Kundeaktiviteter må omfatte følgende:
  - **Primærnøkkel:** Unik identifikator for en aktivitet. For eksempel et besøk på et nettsted eller en bruksoppføring som viser at kunden viste et TV-program.
  - **Tidsstempel:** Dato og klokkeslett for hendelsen som er identifisert ved hjelp av primærnøkkelen.
  - **Hendelse:** Navnet på hendelsen du vil bruke. Et felt kalt "UserAction" i en strømmevideotjeneste kan for eksempel ha verdien "Vist".
  - **Detaljer:** Detaljert informasjon om hendelsen. Et felt kalt "ShowTitle" i en strømmevideotjeneste kan for eksempel ha verdien for en video som kunden har sett på.
- Mindre enn 20 % av manglende verdier i datafeltet for den angitte enheten.

## <a name="create-a-subscription-churn-prediction"></a>Opprette en forutsigelse av abonnementsfrafall

Velg **Lagre utkast** når som helst for å lagre prediksjonen som utkast. Ukastprediksjonen vises i fanen **Mine prediksjoner**.

1. Gå til **Intelligens** > **Prediksjoner**.

1. Velg **Bruk modell** på flisen **Modell for kundefrafall** i **Opprett**-fanen.

1. Velg **Abonnement** for frafallstypen og deretter **Kom i gang**.

1. **Gi navn til denne modellen** og **Navn på utdataenheten** for å skille dem fra andre modeller eller enheter.

1. Velg **Neste**.

### <a name="define-customer-churn"></a>Definer kundefrafall

1. Angi et antall for **Dager siden abonnement ble avsluttet** som bedriften anser at en kunde er i frafalt tilstand. Denne perioden er vanligvis knyttet til forretningsaktiviteter som tilbud eller andre markedsføringstiltak som prøver å hindre at bedriften mister kunden.

1. Angi antall **Dager det skal søkes inn i fremtid for å forutsi frafall**. Du kan for eksempel forutse risikoen for frafall for kundene dine i løpet av de neste 90 dagene, for å rette inn tiltak for å beholde kundene i markedsføringen. Å forutsi frafallsrisiko i lengre eller kortere perioder kan gjøre det vanskeligere å håndtere faktorene i profilen for frafallsrisiko, avhengig av dine spesielle forretningskrav.

1. Velg **Neste**.

### <a name="add-required-data"></a>Legg til obligatoriske data

1. Velg **Legg til data** for **Abonnementslogg**.

1. Velg den semantiske aktivitetstypen **Abonnement** som inneholder den nødvendige abonnementslogginformasjonen. Hvis aktiviteten ikke er konfigurert, velger du **her** og oppretter den.

1. Hvis aktivitetsattributtene ble tilordnet semantisk da aktiviteten ble opprettet, velger du de bestemte attributtene eller enheten du vil at beregningen skal fokusere på, under **Aktiviteter**. Hvis semantisk tilordning ikke forekom, velger du **Rediger** og tilordner dataene.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Legg til nødvendige data for Modell for abonnementsfrafall":::

1. Velg **Neste**, og se gjennom attributtene som kreves for denne modellen.

1. Velg **Lagre**.

1. Velg **Legg til data** for **Kundeaktiviteter**.

1. Velg den semantiske aktivitetstypen som inneholder kundeaktivitetsinformasjon. Hvis aktiviteten ikke er konfigurert, velger du **her** og oppretter den.

1. Hvis aktivitetsattributtene ble tilordnet semantisk da aktiviteten ble opprettet, velger du de bestemte attributtene eller enheten du vil at beregningen skal fokusere på, under **Aktiviteter**. Hvis semantisk tilordning ikke forekom, velger du **Rediger** og tilordner dataene.

1. Velg **Neste**, og se gjennom attributtene som kreves for denne modellen.

1. Velg **Lagre**.

1. Legg til flere aktiviteter, eller velg **Neste**.

### <a name="set-update-schedule"></a>Angi oppdateringstidsplan

1. Velg hyppigheten for å lære opp modellen på nytt. Denne innstillingen er viktig for å oppdatere nøyaktigheten av prognoser når nye data inntas i Customer Insights. De fleste virksomheter kan gjenopplære én gang i måneden og få god nøyaktighet for prognosen.

1. Velg **Neste**.

### <a name="review-and-run-the-model-configuration"></a>Se gjennom og kjøre modellkonfigurasjonen

Trinnet **Se gjennom og kjør** viser et sammendrag av konfigurasjonen og lar deg gjøre endringer før du oppretter prediksjonen.

1. Velg **Rediger** i et av trinnene for å se gjennom og gjøre endringer.

1. Hvis du er fornøyd med valgene, velger du **Lagre og kjør** for å begynne å kjøre modellen. Velg **Ferdig**. Fanen **Mine prediksjoner** vises mens prediksjon opprettes. Det kan ta flere timer før prosessen er fullført, avhengig av mengden data som brukes i forutsigelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vis prediksjonsresultater

1. Gå til **Intelligens** > **Prediksjoner**.

1. I fanen **Mine prediksjoner** velger du prediksjonen du vil vise.

Det er tre hoveddeler med data på resultatsiden:

- **Ytelse for opplæringsmodell**: Graderingene A, B eller C angir ytelsen til prediksjonen og kan hjelpe deg å ta beslutningen om å bruke resultatene som er lagret i utdataenheten.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Bilde av boksen med informasjon om modellpoengsum med vurdering A.":::

  Vurderinger fastsettes basert på følgende regler:
  - **A** Når modellen har forutsett nøyaktig minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er større enn den historiske gjennomsnittlige frafallsfrekvensen med minst 10 %.
  - **B** Når modellen har forutsett nøyaktig minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er opptil 10 % større enn den historiske gjennomsnittlige frafallsfrekvensen.
  - **C** Når modellen nøyaktig har forutsagt mindre enn 50 % av de totale prognoser, eller når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er mindre enn den historiske gjennomsnittlige frafallsfrekvensen.
  
- **Sannsynligheten for frafall (antall kunder)**: Grupper av kunder basert på den predikerte risikoen for frafall. Du kan eventuelt [opprette kundesegmenter](prediction-based-segment.md) med høy frafallsrisiko. Slike segmenter hjelper deg med å forstå hvor grensen bør gå for segmentmedlemskap.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Diagram som viser fordeling av frafallsresultater, delt opp i områder fra 0 til 100 %":::

- **Mest innflytelsesrike faktorer:** Det er mange faktorer du må ta hensyn til når du oppretter forutsigelsen. Hver av faktorene har sin viktighet beregnet for de aggregerte prognosene som en modell oppretter. Bruk disse faktorene til å validere forutsigelsesresultatene. Eller bruk denne informasjonen senere til å [opprette segmenter](.//prediction-based-segment.md) som kan ha innvirkning på frafallsrisiko for kunder.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Liste med innflytelsesrike faktorer og viktigheten av dem, for å forutsi frafallsresultatet.":::

> [!NOTE]
> I utdataenheten for denne modellen er *ChurnScore* den anslåtte sannsynligheten for frafall, og *IsChurn* er en binær etikett basert på *ChurnScore* med en terskel på 0,5. Hvis denne standardterskelen ikke fungerer for scenarioet ditt, [oppretter du et nytt segment](segments.md) med den foretrukne terskelen. Hvis du vil vise frafallspoengsummen, går du til **Data** > **Enheter** og viser datafanen for utdataenheten du definerte for denne modellen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
