---
title: Prediksjon av transaksjonsfrafall (inneholder video)
description: Forutsi om en kunde er i faresonen for ikke lenger å kjøpe produktene eller tjenestene dine.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610524"
---
# <a name="predict-transaction-churn"></a>Forutsi transaksjonsfrafall

Transaksjonsell frafallsprognose bidrar til å forutse om en kunde ikke lenger kjøper produktene eller tjenestene dine i et gitt tidsvindu.

Du må ha forretningskunnskap for å forstå hva frafall betyr for bedriften din. Vi støtter tidsbaserte frafallsdefinisjoner, som betyr at en kunde anses å ha frafalt etter en periode der det ikke er kjøp.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

For miljøer basert på forretningskontoer kan vi forutsi transaksjonsfrafall for en forretningsforbindelse samt en kombinasjon av forretningsforbindelse og et annet informasjonsnivå, for eksempel produktkategori. Hvis du for eksempel legger til en dimensjon, kan du finne ut hvor sannsynlig det er at forretningsforbindelsen Contoso slutter å kjøpe produktkategorien Kontormateriell. I tillegg kan vi for forretningskontoer også bruke AI til å generere en liste over mulige årsaker til at en forretningsforbindelse sannsynligvis kommer til å gjøre frafall i en kategori med informasjon på sekundært nivå.

> [!TIP]
> Prøv prediksjonen av transaksjonsfrafall ved hjelp av eksempeldata: [Eksempelveiledningen for prediksjon av transaksjonsfrafall](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Forutsetning

- Minst [bidragsytertillatelser](permissions.md).
- Minst 10 kundeprofiler, helst flere enn 1 000 unike kunder.
- Kundeidentifikator, en unik identifikator for å samsvare transaksjoner med kundene.
- Transaksjonsdata for minst det dobbelte av det valgte tidsvinduet, for eksempel transaksjonslogg for to til tre år. Ideelt sett minst to transaksjoner per kunde. Transaksjonsloggen må inneholde følgende:
  - **Transaksjons-ID**: Unik identifikator for et innkjøp eller en transaksjon.
  - **Transaksjonsdato**: Dato for innkjøpet eller transaksjonen.
  - **Verdien av transaksjonen**: Valutabeløpet eller det numeriske verdibeløpet for transaksjonen.
  - **Unik produkt-ID**: ID-en til produktet eller tjenesten som er kjøpt, hvis dataene er på et linjevarenivå.
  - **Om denne transaksjonen var en tilbakeføring**: Et true/false-felt som registrerer om transaksjonen var en retur eller ikke. Hvis **Verdien av transaksjonen** er negativ, utleder vi en retur.
- Kundeaktivitetsdata:
  - Kundeidentifikator, en unik identifikator for å tilordne aktiviteter til kunder.
  - **Primærnøkkel:** Unik identifikator for en aktivitet. Et besøk på et nettsted eller en bruksoppføring som for eksempel viser at kunden prøvde et prøveeksemplar av produktet ditt.
  - **Tidsstempel:** Dato og klokkeslett for hendelsen som er identifisert ved hjelp av primærnøkkelen.
  - **Hendelse:** Navnet på hendelsen du vil bruke. Et felt kalt "Brukerhandling" i en dagligvareforretning kan for eksempel være en kupong som brukes av kunden.
  - **Detaljer:** Detaljert informasjon om hendelsen. Et felt kalt "Kupongverdi" i et dagligvareforretning kan for eksempel være valutaverdien for kupongen.
- Mindre enn 20 % av manglende verdier i datafeltet for den angitte enheten

Når det gjelder forretningsforbindelser (B2B), legger du til kundedata innrettet mot mer statiske attributter for å sikre at modellen yter best mulig:
- **CustomerID:** Unik identifikator for en kunde.
- **Opprettingsdato:** Datoen da kunden opprinnelig ble lagt til.
- **Delstat eller område:** Delstaten eller området til en kunde.
- **Land:** Landet til en kunde.
- **Bransje:** Bransjetypen til en kunde. Et felt kalt Bransje for en kaffebrenner kan for eksempel angi om kunden var detaljist.
- **Klassifisering:** Kategoriseringen av en kunde for virksomheten. Et felt som kalles "ValueSegment" for en kaffebrenner, kan for eksempel være kundenivået basert på kundestørrelsen.

> [!NOTE]
> For en bedrift med høy kundekjøpsfrekvens (med noen få ukers mellomrom) anbefales det å velge et kortere prediksjonsvindu og frafallsdefinisjon. For lav kjøpsfrekvens (med noen få måneders mellomrom eller en gang i året) velger du en lengre prediksjonsvindu og frafallsdefinisjon.

## <a name="create-a-transaction-churn-prediction"></a>Opprette en prediksjon av transaksjonsfrafall

1. Gå til **Intelligens** > **Prediksjoner**.

1. Velg **Bruk modell** på flisen **Modell for kundefrafall** i **Opprett**-fanen.

1. Velg **Transaksjon** for frafallstypen og deretter **Kom i gang**.

1. **Gi navn til denne modellen** og **Navn på utdataenheten** for å skille dem fra andre modeller eller enheter.

1. Velg **Neste**.

### <a name="define-customer-churn"></a>Definer kundefrafall

Velg **Lagre utkast** når som helst for å lagre prediksjonen som utkast. Ukastprediksjonen vises i fanen **Mine prediksjoner**.

1. Angi **Prediksjonsvindu**. Du kan for eksempel forutse risikoen for frafall for kundene dine i løpet av de neste 90 dagene, for å rette inn tiltak for å beholde kundene i markedsføringen. Å forutse frafallsrisiko for en lengre eller kortere tidsperiode kan gjøre det vanskeligere å håndtere faktorene i din frafallsrisikoprofil, men det avhenger av dine spesifikke forretningskrav.

1. Angi antallet dager som skal defineres som frafall, i feltet **Frafallsdefinisjon**. Hvis en kunde for eksempel ikke har gjort noen kjøp i løpet av de siste 30 dagene, kan de anses som frafalt for bedriften din.

1. Velg **Neste**.

### <a name="add-purchase-history"></a>Legg til kjøpshistorikk

1. Velg **Legg til data** for **Historikk for kundetransaksjon**.

1. Velg den semantiske aktivitetstypen **SalesOrder** eller **SalesOrderLine**, som inneholder transaksjonslogginformasjonen. Hvis aktiviteten ikke er konfigurert, velger du **her** og oppretter den.

1. Hvis aktivitetsattributtene ble tilordnet semantisk da aktiviteten ble opprettet, velger du de bestemte attributtene eller enheten du vil at beregningen skal fokusere på, under **Aktiviteter**. Hvis semantisk tilordning ikke forekom, velger du **Rediger** og tilordner dataene.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Sideruten som viser hvordan du velger bestemte aktiviteter under semantisk type.":::

1. Velg **Neste**, og se gjennom attributtene som kreves for denne modellen.

1. Velg **Lagre**.

1. Legg til flere aktiviteter, eller velg **Neste**.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Legge til tilleggsdata (valgfritt)

1. Velg **Legg til data** for **Kundeaktiviteter**.

1. Velg den semantiske aktivitetstypen som inneholder dataene du vil bruke. Hvis aktiviteten ikke er konfigurert, velger du **her** og oppretter den.

1. Hvis aktivitetsattributtene ble tilordnet semantisk da aktiviteten ble opprettet, velger du de bestemte attributtene eller enheten du vil at beregningen skal fokusere på, under **Aktiviteter**. Hvis semantisk tilordning ikke forekom, velger du **Rediger** og tilordner dataene.

1. Velg **Neste**, og se gjennom attributtene som kreves for denne modellen.

1. Velg **Lagre**.

1. Velg **Neste**

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Velge prediksjonsnivå

De fleste prediksjoner opprettes på kundenivå. I enkelte situasjoner er det ikke sikkert at dette er detaljert nok til å løse dine forretningsbehov. Bruk denne funksjonen til for eksempel å forutsi frafall for en gren av en kunde, i stedet for kunden som helhet.

1. Velg **Velg enhet for et sekundært nivå**. Hvis alternativet ikke er tilgjengelig, kontrollerer du at du har fullført den forrige delen.

1. Utvid enhetene du vil velge sekundært nivå fra, eller bruk søkefilterboksen til å filtrere de valgte alternativene.

1. Velg attributtet du vil bruke som sekundært nivå, og velg deretter **Legg til**.

1. Velg **Neste**.

> [!NOTE]
> Enhetene som er tilgjengelige i denne delen, vises fordi de har en relasjon til enheten du valgte i forrige del. Hvis enheten du vil legge til, ikke vises, kontrollerer du at den har en gyldig relasjon i **Relasjoner**. Bare én-til-én- og mange-til-én-relasjoner er gyldige for denne konfigurasjonen.

### <a name="add-additional-data-optional"></a>Legge til tilleggsdata (valgfritt)

1. Velg **Legg til data** for **Kundeaktiviteter**.

1. Velg den semantiske aktivitetstypen som inneholder dataene du vil bruke. Hvis aktiviteten ikke er konfigurert, velger du **her** og oppretter den.

1. Hvis aktivitetsattributtene ble tilordnet semantisk da aktiviteten ble opprettet, velger du de bestemte attributtene eller enheten du vil at beregningen skal fokusere på, under **Aktiviteter**. Hvis semantisk tilordning ikke forekom, velger du **Rediger** og tilordner dataene.

1. Velg **Neste**, og se gjennom attributtene som kreves for denne modellen.

1. Velg **Lagre**.

1. Velg **Neste**

1. Du kan eventuelt velge **Legg til data for** for **Kundedata**.

1. Tilordne semantiske attributter til felt i dine egne kundedata som identifisert. Dataene i feltene som brukes, bør ikke endres ofte, for å sikre modellens beste ytelse. Hvis du for eksempel velger et felt for Klassifisering som ble endret hver måned, vil bare den siste verdien i prediksjonen brukes, selv om den samme verdien historisk sett ikke gjelder for kunden ved bygging av prediksjonmønstre.

1. Velg **Neste**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Gi en valgfri liste over referansekontoer

Legg til en liste over forretningskunder og forretningsforbindelser som du vil bruke som referanse. [Detaljer om disse referansekontoene](#view-prediction-results), inkludert deres frafallspoengsum og de mest innflytelsesrike funksjonene som har påvirket deres frafallspoengsum.

1. Velg **+ Legg til kunder**.

1. Velg kundene som fungerer som en referanse.

1. Velg **Neste**.

---

### <a name="set-update-schedule"></a>Angi oppdateringstidsplan

1. Velg hyppigheten for å lære opp modellen på nytt, i trinnet **Dataoppdateringer**. Denne innstillingen er viktig for å oppdatere nøyaktigheten til prediksjoner etter hvert som nye data tas inn i Customer Insights. De fleste virksomheter kan gjenopplære én gang i måneden og få god nøyaktighet for prognosen.

1. Velg **Neste**.

### <a name="review-and-run-the-model-configuration"></a>Se gjennom og kjøre modellkonfigurasjonen

Trinnet **Se gjennom og kjør** viser et sammendrag av konfigurasjonen og lar deg gjøre endringer før du oppretter prediksjonen.

1. Velg **Rediger** i et av trinnene for å se gjennom og gjøre endringer.

1. Hvis du er fornøyd med valgene, velger du **Lagre og kjør** for å begynne å kjøre modellen. Velg **Ferdig**. Fanen **Mine prediksjoner** vises mens prediksjon opprettes. Det kan ta flere timer før prosessen er fullført, avhengig av mengden data som brukes i forutsigelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vis prediksjonsresultater

1. Gå til **Intelligens** > **Prediksjoner**.

1. I fanen **Mine prediksjoner** velger du prediksjonen du vil vise.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

Det er tre hoveddeler med data på resultatsiden:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

Det er tre hoveddeler med data på resultatsiden:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

En informasjonsside med **Innflytelsesrik funksjonsanalyse** inneholder fire deler med data:

- I den høyre ruten velger du et element fra **De beste kundene** eller **Referansekunder**. Begge listene ordnes ved å redusere verdien av frafallspoengsummen, enten poengsummen er bare for kunden eller en kombinert poengsum for kunder og et sekundært nivå som produktkategori. Det valgte elementet bestemmer innholdet på denne siden.

  - **De beste kundene**: Liste over 10 kunder som har høyest risiko for frafall og lavest risiko for frafall basert på kundens frafallspoengsummer.
  - **Referansekunder**: Liste over opptil 10 kunder som ble valgt under konfigurasjon av modellen.

- **Frafallspoengsum**: Viser frafallspoengsummen for det valgte elementet i høyre rute.

- **Frafallsrisikofordeling:** Viser frafallsrisikodistribusjonen på tvers av kunder og persentilet som den valgte kunden er i.

- **Toppfunksjoner som øker eller reduserer frafallsrisiko:** Viser de fem viktigste funksjonene som økte og reduserte frafallsrisikoen, for det valgte elementet i ruten til høyre. Viser verdien av funksjonen for elementet og dens innflytelse på poengsummen for hver innflytelsesrike funksjon. Den gjennomsnittlige verdien av hver funksjon på tvers av segmenter for lave, middels og høye frafallskundesegmenter vises også. Det bidrar til bedre kontekstualisere verdiene for de mest innflytelsesrike funksjonene for det valgte elementet, og sammenligner det med lave, middels og høye kundesegmenter.

  - Lav: forretningsforbindelser eller kombinasjoner av forretningsforbindelse og sekundært nivå med en frafallspoengsum på mellom 0 og 0,33.
  - Middels: forretningsforbindelser eller kombinasjoner av forretningsforbindelser og sekundære nivåer med en frafallspoengsum på mellom 0,33 og 0,66.
  - Høy: forretningsforbindelser eller kombinasjoner av forretningsforbindelser og sekundære nivåer med en frafallspoengsum høyere enn 0,66.

  Når du forutsier frafall på forretningsforbindelsesnivå, vurderes alle forretningsforbindelser ved utlede de gjennomsnittlige funksjonsverdiene for frafallssegmenter. For frafallsprognoser på sekundært nivå for hver forretningsforbindelse avhenger utledingen av frafallssegmenter på sekundært nivå av elementet som er valgt i sideruten. Hvis et element for eksempel har et sekundært produktkategorinivå (kontorrekvisita), vurderes bare elementene som har kontorrekvisita som produktkategorien, når de gjennomsnittlige funksjonsverdiene for frafallssegmenter hentes ut. Denne logikken brukes for å sikre en rettferdig sammenligning av elementets funksjonsverdier med de gjennomsnittlige verdiene på tvers av segmenter med lavt, middels og høyt frafall.

  I noen tilfeller er den gjennomsnittlige verdien av frafallssegmenter med lavt, middels eller høyt nivå, ikke tilgjengelige fordi det ikke finnes elementer som tilhører de tilsvarende frafallssegmentene basert på definisjonen ovenfor.

  Tolkning av verdier under kolonnene for gjennomsnittlig lav, middels og høy er forskjellig for kategoriske funksjoner som land eller bransje. Ettersom anseelsen om gjennomsnittlig funksjonsverdi ikke gjelder kategoriske funksjoner, er verdiene i disse kolonnene en andel av kundene i segmenter med lavt, middels eller høyt frafall som har samme verdi i den kategoriske funksjonen sammenlignet med elementet som er valgt i sidepanelet.

---

 > [!NOTE]
 > I utdataenheten for denne modellen viser *ChurnScore* den anslåtte sannsynligheten for frafall, og *IsChurn* er en binær etikett basert på *ChurnScore* med en terskel på 0,5. Hvis denne standardterskelen ikke fungerer for scenarioet ditt, [oppretter du et nytt segment](segments.md#create-a-segment) med den foretrukne terskelen. Ikke alle kunder er nødvendigvis aktive kunder. Noen av dem har kanskje ikke hatt noen aktivitet på lenge og anses som frafalt allerede, basert på din frafallsdefinisjon. Å forutsi frafallsrisiko for kunder som allerede er frafalt, er ikke nyttig fordi de ikke er en interessant målgruppe.
>
> Hvis du vil vise frafallspoengsummen, går du til **Data** > **Enheter** og viser datafanen for utdataenheten du definerte for denne modellen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
