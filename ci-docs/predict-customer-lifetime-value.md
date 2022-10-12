---
title: Forutsi kundens levetidsverdi (CLV)
description: Forutsi omsetningspotensialet for aktive kunder i fremtiden.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610386"
---
# <a name="predict-customer-lifetime-value-clv"></a>Forutsi kundens levetidsverdi (CLV)

Forutsi potensiell verdi (omsetning) som individuelle aktive kunder kommer til å innføre i virksomheten i løpet av en definert fremtidig tidsperiode. Denne prediksjonen hjelper deg med følgende:

- identifisere verdifulle kunder og behandle denne innsikten
- opprette strategiske kundesegmenter basert på potensiell verdi for å kjøre tilpassede kampanjer med målrettet innsats for salg, markedsføring og støtte
- veilede produktutvikling ved å fokusere på funksjoner som øker kundeverdien
- optimalisere salgs- eller markedsføringsstrategi og tildele budsjett mer nøyaktig for kundeoppsøking
- gjenkjenne og belønne kunder med høy verdi gjennom lojalitets- eller belønningsprogrammer

Finn ut hva CLV betyr for virksomheten. Vi støtter transaksjonsbasert CLV-prediksjon. Den beregnede verdien for en kunde er basert på loggen over forretningstransaksjoner. Vurder å opprette flere modeller med varierende inndatainnstillinger og sammenligne modellresultater for å se hvilket modellscenario som passer best til dine forretningsbehov.

> [!TIP]
> Prøv CLV-prediksjonen ved å bruke eksempeldata: [Eksempelveiledning for prediksjon av kundens levetidsverdi (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Forutsetning

- Minst [Bidragsyter](permissions.md)-tillatelser
- Minst 100 unike kunder, helst flere enn 10 000 kunder
- Kundeidentifikator, en unik identifikator for å samsvare transaksjoner med en individuell kunde
- Transaksjonslogg for minst ett år, men helst to til tre år. Ideelt sett minst to til tre transaksjoner per kunde-ID, helst på tvers av flere datoer. Transaksjonsloggen må inneholde følgende:
  - **Transaksjons-ID**: unik identifikator for hver transaksjon
  - **Transaksjonsdato**: dato- eller tidsstempel for hver transaksjon
  - **Transaksjonsbeløp**: pengeverdi (for eksempel omsetning eller fortjenestemargin) for hver transaksjon
  - **Etikett tilordnet til returer**: boolsk true/false-verdi som angir om transaksjonen er en retur
  - **Produkt-ID**: produkt-ID for produktet involvert i transaksjonen
- Data om kundeaktiviteter:
  - **Primærnøkkel**: unik identifikator for en aktivitet
  - **Tidsstempel**: dato og klokkeslett for hendelsen som er identifisert ved hjelp av primærnøkkelen
  - **Hendelse (aktivitetsnavn)**: navn på hendelsen du vil bruke
  - **Detaljer (beløp eller verdi)**: Detaljer om kundeaktiviteten
- Tilleggsdata, for eksempel følgende:
  - Nettaktiviteter: logg for nettstedsbesøk eller e-post
  - Lojalitetsaktiviteter: avsetning av lojalitetspoeng og innløsningslogg
  - Kundeservicelogg: servicesamtale, klage eller returhistorikk
  - Informasjon om kundeprofil
- Mindre enn 20 % manglende verdier i obligatoriske felt

> [!NOTE]
> Bare én transaksjonsloggenhet kan konfigureres. Hvis det finnes flere kjøps- eller transaksjonsenheter, kombinerer du dem i Power Query før datainntak begynner.

## <a name="create-a-customer-lifetime-value-prediction"></a>Opprett en prediksjon av verdi for kundelevetid

Velg **Lagre utkast** når som helst for å lagre prediksjonen som utkast. Ukastprediksjonen vises i fanen **Mine prediksjoner**.

1. Gå til **Intelligens** > **Prediksjoner**.

1. Velg **Bruk modell** på flisen **Kundens levetidsverdi** i **Opprett**-fanen.

1. Velg **Komme i gang**.

1. **Gi navn til denne modellen** og **Navn på utdataenheten** for å skille dem fra andre modeller eller enheter.

1. Velg **Neste**.

### <a name="define-model-preferences"></a>Definer modellinnstillinger

1. Angi en **prediksjonstidsperiode** for å definere hvor langt inn i fremtiden du vil forutsi CLV. Enheten angis som standard som måneder.

   > [!TIP]
   > For å kunne forutsi CLV nøyaktig for angitt tidsperiode, trenger du en sammenlignbar periode med historiske data. Hvis du for eksempel vil forutsi CLV for de neste 12 månedene, må du ha minst 18–24 måneder med historiske data.

1. Angi tidsramme der en kunde må ha hatt minst én transaksjon for å bli betraktet som aktiv. Modellen forutsier bare CLV for **Aktive kunder**.
   - **La modell beregne kjøpsintervall (anbefales)**: Modellen analyserer dataene og bestemmer en tidsperiode basert på historiske kjøp.
   - **Angi intervall manuelt**: Tidsperioden for definisjonen av en aktiv kunde.

1. Definer persentilet for **Kunde med høy verdi**.
    - **Modellberegning (anbefales)**: Modellen bruker 80/20-regelen. Prosentandel av kunder som bidro til 80 % akkumulert omsetning for virksomheten i den historiske perioden, regnes som kunder med høy verdi. Vanligvis bidrar mindre enn 30–40 % kunder til 80 % akkumulert omsetning. Dette antallet kan imidlertid variere avhengig av virksomheten og bransjen.
    - **Prosent av de mest aktive kundene**: Bestemt persentil for en kunde med høy verdi. Du kan for eksempel angi **25** for å definere kunder med høy verdi som topp 25 % av fremtidige betalende kunder.

    Hvis virksomheten din definerer kunder med høy verdi på en annen måte, må du [gi oss beskjed for det vil vi gjerne høre om](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Velg **Neste**.

### <a name="add-required-data"></a>Legg til obligatoriske data

1. Velg **Legg til data** for **Historikk for kundetransaksjon**.

1. Velg den semantiske aktivitetstypen **SalesOrder** eller **SalesOrderLine**, som inneholder transaksjonsloggen. Hvis aktiviteten ikke er konfigurert, velger du **her** og oppretter den.

1. Hvis aktivitetsattributtene ble tilordnet semantisk da aktiviteten ble opprettet, velger du de bestemte attributtene eller enheten du vil at beregningen skal fokusere på, under **Aktiviteter**. Hvis semantisk tilordning ikke forekom, velger du **Rediger** og tilordner dataene.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Legg til nødvendige data for CLV-modell":::

1. Velg **Neste**, og se gjennom attributtene som kreves for denne modellen.

1. Velg **Lagre**.

1. Legg til flere aktiviteter, eller velg **Neste**.

### <a name="add-optional-activity-data"></a>Legg til valgfrie aktivitetsdata

Data som gjenspeiler viktige samhandlinger med kunder (for eksempel nett, kundeservice og hendelseslogger), legger til kontekst i transaksjonsoppføringer. Flere mønstre som finnes i kundeaktivitetsdataene, kan forbedre nøyaktigheten av prediksjonene.

1. Velg **Legg til data** under **Øk innsikten i modellen med flere aktivitetsdata**.

1. Velg en aktivitetstype som samsvarer med typen kundeaktivitet du legger til. Hvis aktiviteten ikke er konfigurert, velger du **her** og oppretter den.

1. Hvis aktivitetsattributtene ble tilordnet da aktiviteten ble opprettet, velger du de bestemte attributtene eller enheten du vil at beregningen skal fokusere på, under **Aktiviteter**. Hvis tilordning ikke forekom, velger du **Rediger** og tilordner dataene.

1. Velg **Neste**, og se gjennom attributtene som kreves for denne modellen.

1. Velg **Lagre**.

1. Velg **Neste**.

1. [Legg til valgfrie kundedata](#add-optional-customer-data), eller velg **Neste** og gå til [Angi oppdateringstidsplan](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Legg til valgfrie kundedata

Velg blant 18 ofte brukte kundeprofilattributter du vil ta med som inndata i modellen. Disse attributtene kan gi mer tilpassede, relevante og handlingsrettede modellresultater for forretningsbrukstilfellene.

Eksempel: Contoso Coffee ønsker å forutsi kundens levetidsverdi for å tilby kunder med høy verdi et tilpasset tilbud knyttet til lanseringen av den nye espressomaskinen deres. Contoso bruker CLV-modellen og legger til alle de 18 kundeprofilattributtene for å se hvilke faktorer som påvirker kundene med høyest verdi. De finner at kundested er den mest innflytelsesrike faktoren for disse kundene.
Basert på denne informasjonen organiserer de et lokalt arrangement for lanseringen av espressomaskinen og samarbeider med lokale leverandører for å tilby tilpassede tilbud og en spesiell opplevelse på arrangementet. Uten denne informasjonen hadde kanskje Contoso bare ha sendt generisk markedsførings-e-post og gått glipp av muligheten til å tilpasse arrangementet for dette lokale segmentet med kunder med høy verdi.

1. Velg **Legg til data** under **Øk innsikten i modellen med enda flere kundedata**.

1. Velg **Customer: CustomerInsights** for **Enhet** for å velge den enhetlige kundeprofilen som tilordnes til kundeattributtdata. Velg **System.Customer.CustomerId** for **Kunde-ID**.

1. Tilordne flere felter hvis dataene er tilgjengelige i de enhetlige kundeprofilene.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Eksempel på tilordnede felter for kundeprofildata.":::

1. Velg **Lagre**.

1. Velg **Neste**.

### <a name="set-update-schedule"></a>Angi oppdateringstidsplan

1. Velg hyppigheten for å lære opp modellen på nytt basert på de nyeste dataene. Denne innstillingen er viktig for å oppdatere nøyaktigheten til prediksjoner etter hvert som nye data tas inn i Customer Insights. De fleste virksomheter kan gjenopplære én gang i måneden og få god nøyaktighet for prognosen.

1. Velg **Neste**.

### <a name="review-and-run-the-model-configuration"></a>Se gjennom og kjøre modellkonfigurasjonen

Trinnet **Se gjennom og kjør** viser et sammendrag av konfigurasjonen og lar deg gjøre endringer før du oppretter prediksjonen.

1. Velg **Rediger** i et av trinnene for å se gjennom og gjøre endringer.

1. Hvis du er fornøyd med valgene, velger du **Lagre og kjør** for å begynne å kjøre modellen. Velg **Ferdig**. Fanen **Mine prediksjoner** vises mens prediksjon opprettes. Det kan ta flere timer før prosessen er fullført, avhengig av mengden data som brukes i forutsigelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vis prediksjonsresultater

1. Gå til **Intelligens** > **Prediksjoner**.

1. I fanen **Mine prediksjoner** velger du prediksjonen du vil vise.

Det er tre hoveddeler med data på resultatsiden.

- **Ytelse for opplæringsmodell**: Graderingene A, B eller C angir ytelsen til prediksjonen og kan hjelpe deg å ta beslutningen om å bruke resultatene som er lagret i utdataenheten.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Bilde av boksen med informasjon om modellpoengsum med vurdering A.":::

  Customer Insights vurderer ytelsen til modellen for kunstig intelligens når det gjelder å forutsi kundene med høy verdi, sammenlignet med en basismodell.

  Vurderinger fastsettes basert på følgende regler:
  - **A** når modellen nøyaktig beregnet minst 5 % flere kunder med høy verdi sammenlignet med basismodellen.
  - **B** når modellen nøyaktig beregnet mellom 0–5 % flere kunder med høy verdi sammenlignet med basismodellen.
  - **C** når modellen nøyaktig beregnet færre kunder med høy verdi sammenlignet med basismodellen.
  
  Velg [**Finn ut mer om denne poengsummen**](#learn-about-the-score) for å åpne ruten **Modellrangering**, som viser flere detaljer om ytelsen til modellen for kunstig intelligens og basismodellen. Det gir deg en bedre forståelse av de underliggende måleverdiene for modellytelse og hvordan den endelige ytelsesgraden for modellen ble utledet. Basismodellen bruker en ikke-AI-basert metode til å beregne verdie for kundelevetid, basert primært på historiske kjøp gjort av kunder.

- **Verdien av kundene etter persentil**: Kunder med lav verdi og høy verdi vises i et diagram. Hold musepekeren over stolpene i histogrammet for å se antall kunder i hver gruppe og den gjennomsnittlige CLV-en for gruppen. Du kan alternativt [opprette kundesegmenter](prediction-based-segment.md) basert på CLV-prediksjonene deres.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Verdien av kundene etter persentil for CLV-modell":::

- **Mest innflytelsesrike faktorer**: Ulike faktorer vurderes når du oppretter CLV-prediksjon basert på inndataene som gis til modellen for kunstig intelligens. Hver av faktorene har sin viktighet beregnet for de aggregerte prognoser som opprettes av en modell. Bruk disse faktorene til å validere forutsigelsesresultatene. Disse faktorene gir også mer innsikt i de mest innflytelsesrike faktorene som bidro til å forutsi CLV for alle kundene.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Mest innflytelsesrike faktorer for CLV-modell":::

### <a name="learn-about-the-score"></a>Finn ut mer om poengsummen

Standardformelen som brukes til å beregne CLV etter basismodellen:

 _**CLV for hver kunde** = Gjennomsnittlig månedlig kjøp gjort av kunden i det aktive kundevinduet * antall måneder i CLV-prediksjonsperioden * total oppbevaringsgrad for alle kunder_

Modellen for kunstig intelligens sammenlignes med basismodellen basert på to måleverdier for modellytelse.
  
- **Prediksjonssuksess for kunder med høy verdi**

  Se forskjellen mellom å forutsi kunder med høy verdi ved hjelp av modellen for kunstig intelligens sammenlignet med basismodellen. Suksessrate på 84 % betyr for eksempel at av alle kunder med høy verdi i opplæringsdataene, kunne modellen for kunstig intelligens nøyaktig fange opp 84 %. Deretter sammenligner vi suksessgraden med suksessgraden for basismodellen for å rapportere den relative endringen. Denne verdien brukes til å tilordne en vurdering til modellen.

- **Feilmåleverdier**

  Gå gjennom den totale ytelsen til modellen i form av feil når du skal forutsi fremtidige verdier. Vi bruker den totale RMSE-måleverdien (Root Mean Squared Error) til å vurdere denne feilen. RMSE er en standardmetode for å måle feilen for en modell ved prediksjon av kvantitative data. RMSE for modellen for kunstig intelligens sammenlignes med RMSE for basismodellen, og den relative forskjellen rapporteres.

Modellen for kunstig intelligens prioriterer nøyaktig rangering av kunder i henhold til verdien de gir til virksomheten. Så bare suksessfrekvensen for å forutsi kunder med høy verdi brukes til å få den endelige modellgraden. RMSE-måleverdien er sensitiv for fordreininger. I scenarioer der du har en liten prosentandel av kundene med usedvanlig høye kjøpsverdier, kan det hende at den samlede RMSE-måleverdien ikke gir et fullstendig bilde av modellytelsen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
