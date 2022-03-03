---
title: Prediksjon for transaksjonsfrafall (inneholder video)
description: Forutsi om en kunde er i faresonen for ikke lenger å kjøpe produktene eller tjenestene dine.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 9aa208ad94dcb6b1e0f110a3f974c56de00bbd07
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355671"
---
# <a name="transaction-churn-prediction"></a>Prediksjon for transaksjonsfrafall

Transaksjonsell frafallsprognose bidrar til å forutse om en kunde ikke lenger kjøper produktene eller tjenestene dine i et gitt tidsvindu. Du kan opprette nye frafallsprognoser under **Intelligens** > **Prognoser**. Velg **Mine prediksjoner** for å se andre prediksjoner du har opprettet. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

For miljøer basert på forretningskontoer kan vi forutsi transaksjonsfrafall for en forretningsforbindelse samt en kombinasjon av forretningsforbindelse og et annet informasjonsnivå, for eksempel produktkategori. Ved å legge til en dimensjon kan du finne ut hvor sannsynlig det er at forretningsforbindelsen Contoso slutter å kjøpe produktkategorien Kontormateriell. I tillegg kan vi for forretningskontoer også bruke AI til å generere en liste over mulige årsaker til at en forretningsforbindelse sannsynligvis kommer til å gjøre frafall i en kategori med informasjon på sekundært nivå.

> [!TIP]
> Prøv opplæringen for prediksjon for transaksjonsfrafall ved hjelp av eksempeldata: [Eksempelveiledningen Prediksjon for transaksjonsfrafall](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Krav

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

- Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.
- Forretningskunnskap for å forstå hva frafall betyr for bedriften din. Vi støtter tidsbaserte frafallsdefinisjoner, som betyr at en kunde anses å ha frafalt etter en periode der det ikke er kjøp.
- Data om dine transaksjoner/kjøp og deres historikk:
    - Transaksjons-ID-er for å skille innkjøp/transaksjoner.
    - Kunde-ID-er for å samsvare transaksjoner for kundene.
    - Dato for transaksjonshendelser, som definerer datoene da transaksjonen forekom.
    - Det semantiske dataskjemaet for kjøp/transaksjoner krever følgende informasjon:
        - **Transaksjons-ID**: En unik identifikator for et innkjøp eller en transaksjon.
        - **Transaksjonsdato**: Datoen for innkjøpet eller transaksjonen.
        - **Verdien av transaksjonen**: Valutabeløpet / det numeriske verdibeløpet for transaksjonen/varen.
        - (Valgfritt) **Unik produkt-ID**: ID-en til produktet eller tjenesten som er kjøpt, hvis dataene er på et linjevarenivå.
        - (Valgfritt) **Om denne transaksjonen var en tilbakeføring**: Et sant/usant-felt som registrerer om transaksjonen var en retur eller ikke. Hvis **Verdien av transaksjonen** er negativ, vil vi også bruke denne informasjonen til å utlede en retur.
- (Valgfritt) Data om kundeaktiviteter:
    - Aktivitets-ID-er for å skille mellom aktiviteter av samme type.
    - Kunde-ID-er for å tilordne aktiviteter til kundene.
    - Aktivitetsinformasjon som inneholder navnet på og datoen for aktiviteten.
    - Det semantiske dataskjemaet for kundeaktiviteter omfatter følgende:
        - **Primærnøkkel:** En unik identifikator for en aktivitet. Et besøk på et nettsted eller en bruksoppføring som for eksempel viser at kunden prøvde et prøveeksemplar av produktet ditt.
        - **Tidsstempel:** Dato og klokkeslett for hendelsen som er identifisert ved hjelp av primærnøkkelen.
        - **Hendelse:** Navnet på hendelsen du vil bruke. Et felt kalt "Brukerhandling" i en dagligvareforretning kan for eksempel være en kupong som brukes av kunden.
        - **Detaljer:** Detaljert informasjon om hendelsen. Et felt kalt "Kupongverdi" i et dagligvareforretning kan for eksempel være valutaverdien for kupongen.

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

- Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.
- Forretningskunnskap for å forstå hva frafall betyr for bedriften din. Vi støtter tidsbaserte frafallsdefinisjoner, som betyr at en kunde anses å ha frafalt etter en periode der det ikke er kjøp.
- Data om dine transaksjoner/kjøp og deres historikk:
    - Transaksjons-ID-er for å skille innkjøp/transaksjoner.
    - Kunde-ID-er for å samsvare transaksjoner for kundene.
    - Dato for transaksjonshendelser, som definerer datoene da transaksjonen forekom.
    - Det semantiske dataskjemaet for kjøp/transaksjoner krever følgende informasjon:
        - **Transaksjons-ID**: En unik identifikator for et innkjøp eller en transaksjon.
        - **Transaksjonsdato**: Datoen for innkjøpet eller transaksjonen.
        - **Verdien av transaksjonen**: Valutabeløpet / det numeriske verdibeløpet for transaksjonen/varen.
        - (Valgfritt) **Unik produkt-ID**: ID-en til produktet eller tjenesten som er kjøpt, hvis dataene er på et linjevarenivå.
        - (Valgfritt) **Om denne transaksjonen var en tilbakeføring**: Et sant/usant-felt som registrerer om transaksjonen var en retur eller ikke. Hvis **Verdien av transaksjonen** er negativ, vil vi også bruke denne informasjonen til å utlede en retur.
- (Valgfritt) Data om kundeaktiviteter:
    - Aktivitets-ID-er for å skille mellom aktiviteter av samme type.
    - Kunde-ID-er for å tilordne aktiviteter til kundene.
    - Aktivitetsinformasjon som inneholder navnet på og datoen for aktiviteten.
    - Det semantiske dataskjemaet for kundeaktiviteter omfatter følgende:
        - **Primærnøkkel:** En unik identifikator for en aktivitet. Et besøk på et nettsted eller en bruksoppføring som for eksempel viser at kunden prøvde et prøveeksemplar av produktet ditt.
        - **Tidsstempel:** Dato og klokkeslett for hendelsen som er identifisert ved hjelp av primærnøkkelen.
        - **Hendelse:** Navnet på hendelsen du vil bruke. Et felt kalt "Brukerhandling" i en dagligvareforretning kan for eksempel være en kupong som brukes av kunden.
        - **Detaljer:** Detaljert informasjon om hendelsen. Et felt kalt "Kupongverdi" i et dagligvareforretning kan for eksempel være valutaverdien for kupongen.
- (Valgfritt) Data om kundene:
    - Disse dataene skal justeres mot mer statiske attributter for å sikre at modellen yter best mulig.
    - Det semantiske dataskjemaet for kundedata omfatter følgende:
        - **CustomerID:** Unik identifikator for en kunde.
        - **Opprettet dato:** Datoen da kunden opprinnelig ble lagt til.
        - **Delstat eller område:** Staten eller området til en kunde.
        - **Land:** Landet til en kunde.
        - **Bransje:** Bransjetypen til en kunde. Et felt kalt Bransje for en kaffebrenner kan for eksempel angi om kunden var detaljist.
        - **Klassifisering:** Kategoriseringen av en kunde for virksomheten. Et felt som kalles "ValueSegment" for en kaffebrenner, kan for eksempel være kundenivået basert på kundestørrelsen.

---

- Kjennetegn for foreslåtte data:
    - Tilstrekkelige historiske data: Transaksjonsdata for minst det dobbelte av det valgte tidsvinduet. Helst to til tre år med transaksjonslogg. 
    - Flere kjøp per kunde: Ideelt minst to transaksjoner per kunde.
    - Antall kunder: Minst 10 kundeprofiler, helst mer enn 1 000 unike kunder. Modellen vil mislykkes med færre enn 10 kunder og utilstrekkelige historiske data.
    - Datafullføring: Mindre enn 20 % av manglende verdier i datafeltet for den angitte enheten.

> [!NOTE]
> For en bedrift med høy kundekjøpsfrekvens (med noen få ukers mellomrom) anbefales det å velge et kortere prediksjonsvindu og frafallsdefinisjon. For lav kjøpsfrekvens (med noen få måneders mellomrom eller en gang i året) velger du en lengre prediksjonsvindu og frafallsdefinisjon.

## <a name="create-a-transaction-churn-prediction"></a>Opprette en prediksjon for transaksjonsfrafall

1. Gå til **Intelligens** > **Prognoser** i Customer Insights.

1. Velg flisen **Modell for kundefrafall** og velg **Bruk denne modellen**.

1. I ruten **Modell for kundefrafall** velger du **Transaksjon**, og deretter velger du **Start**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Skjermbilde med det valgte transaksjonsalternativet i ruten Modell for kundefrafall.":::
 
### <a name="name-model"></a>Gi navn til modell

1. Angi et navn på modellen for å skille den fra andre modeller.

1. Angi et navn for utdataenheten bare ved hjelp av bokstaver og tall, uten mellomrom. Det er navnet som modellenheten vil bruke. 

1. Velg **Neste**.

### <a name="define-customer-churn"></a>Definer kundefrafall

1. Angi **Prediksjonsvindu**. Du kan for eksempel forutse risikoen for frafall for kundene dine i løpet av de neste 90 dagene, for å rette inn tiltak for å beholde kundene i markedsføringen. Å forutse frafallsrisiko for en lengre eller kortere tidsperiode kan gjøre det vanskeligere å håndtere faktorene i din frafallsrisikoprofil, men det avhenger av dine spesifikke forretningskrav.
   >[!TIP]
   > Du kan velge **Lagre utkast** når som helst for å lagre prediksjonen som utkast. Du finner utkastforutsigelsen i **Mine prediksjoner**-fanen for å fortsette.

1. Angi antallet dager som skal defineres som frafall, i feltet **Frafallsdefinisjon**. Hvis for eksempel en kunde ikke har gjort noen kjøp i løpet av de siste 30 dagene, kan de anses som frafalt for bedriften din. 

1. Velg **Neste** for å fortsette.

### <a name="add-required-data"></a>Legg til obligatoriske data

1. Velg **Legg til data**, og velg aktivitetstypen i sideruten som inneholder den nødvendige informasjonen om transaksjonen eller innkjøpsloggen.

1. Velg de bestemte aktivitetene fra den valgte aktivitetstypen du vil at beregningen skal fokusere på, under **Velg aktiviteter**.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Sideruten som viser hvordan du velger bestemte aktiviteter under semantisk type.":::

   Hvis du ikke har tilordnet aktiviteten til en semantisk type ennå, velger du **Rediger** for å gjøre dette. Den veiledede opplevelsen for kartlegging av semantiske aktiviteter åpnes. Tilordne dataene til de tilsvarende feltene i den valgte aktivitetstypen.

1. Tilordne semantiske attributter til feltene som kreves for å kjøre modellen. Hvis feltene nedenfor ikke fylles ut, konfigurerer du relasjonen fra kjøpsloggenheten til enheten *Kunde*. Velg **Lagre**.

1. Velg **Neste** i trinnet **Legg til obligatoriske data** for å fortsette hvis du ikke vil legge til flere aktiviteter.


# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Legge til tilleggsdata (valgfritt)

Konfigurer relasjonen fra kundeaktivitetsenheten til *kundeenheten*.

1. Velg feltet som identifiserer kunden i kundeaktivitetstabellen. Den kan være direkte relatert til den primære kunde-ID-en til *kundeenheten*.

1. Velg enheten som er hovedenhet for enheten *Kunde*.

1. Angi et navn som beskriver relasjonen.

#### <a name="customer-activities"></a>Kundeaktiviteter

1. Du kan eventuelt velge **Legg til data** for **Kundeaktiviteter**.

1. Velg den semantiske aktivitetstypen som inneholder dataene du vil bruke, og velg deretter én eller flere aktiviteter i **Aktiviteter**-delen.

1. Velg en aktivitetstype som samsvarer med typen kundeaktivitet du skal konfigurere. Velg **Opprett ny**, og velg en tilgjengelig aktivitetstype, eller opprett en ny type.

1. Velg **Neste** og deretter **Lagre**.

1. Hvis du har andre kundeaktiviteter som du vil ha med, gjentar du fremgangsmåten ovenfor.

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Velge prediksjonsnivå

De fleste prediksjoner opprettes på kundenivå. I enkelte situasjoner er det ikke sikkert at dette er detaljert nok til å løse dine forretningsbehov. Du kan bruke denne funksjonen til å forutsi forfall for en gren av en kunde, for eksempel i stedet for kunden som helhet.

1. Hvis du vil opprette en prediksjon på et mer detaljert nivå enn kunden, velger du **Velg enhet for et sekundært nivå**. Hvis alternativet ikke er tilgjengelig, kontrollerer du at du har fullført den forrige delen.

1. Utvid enhetene du vil velge sekundært nivå fra, eller bruk søkefilterboksen til å filtrere de valgte alternativene.

1. Velg attributtet du vil bruke som sekundært nivå, og velg deretter **Legg til**.

1. Velg **Neste**.

> [!NOTE]
> Enhetene som er tilgjengelige i denne delen, vises fordi de har en relasjon til enheten du valgte i forrige del. Hvis enheten du vil legge til, ikke vises, kontrollerer du at den har en gyldig relasjon i **Relasjoner**. Bare én-til-én- og mange-til-én-relasjoner er gyldige for denne konfigurasjonen.

### <a name="add-additional-data-optional"></a>Legge til tilleggsdata (valgfritt)

Konfigurer relasjonen fra kundeaktivitetsenheten til *kundeenheten*.

1. Velg feltet som identifiserer kunden i kundeaktivitetstabellen. Den kan være direkte relatert til den primære kunde-ID-en til *kundeenheten*.

1. Velg enheten som er hovedenhet for enheten *Kunde*.

1. Angi et navn som beskriver relasjonen.

#### <a name="customer-activities"></a>Kundeaktiviteter

1. Du kan eventuelt velge **Legg til data** for **Kundeaktiviteter**.

1. Velg den semantiske aktivitetstypen som inneholder dataene du vil bruke, og velg deretter én eller flere aktiviteter i **Aktiviteter**-delen.

1. Velg en aktivitetstype som samsvarer med typen kundeaktivitet du skal konfigurere. Velg **Opprett ny**, og velg en tilgjengelig aktivitetstype, eller opprett en ny type.

1. Velg **Neste** og deretter **Lagre**.

1. Hvis du har andre kundeaktiviteter som du vil ha med, gjentar du fremgangsmåten ovenfor.

#### <a name="customers-data"></a>Kundedata

1. Du kan eventuelt velge **Legg til data for** for **Kundedata**.

1. Tilordne semantiske attributter til felt i dine egne kundedata som identifisert. Dataene i feltene som brukes, bør ikke endres ofte, for å sikre modellens beste ytelse. Hvis du for eksempel velger et felt for Klassifisering som ble endret hver måned, vil bare den siste verdien i prediksjonen brukes, selv om den samme verdien historisk sett ikke gjelder for kunden ved bygging av prediksjonmønstre.

1. Velg **Neste**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Gi en valgfri liste over referansekontoer

Legg til en liste over forretningskunder og forretningsforbindelser som du vil bruke som referanse. Du får [detaljer om disse referansekontoene](#review-a-prediction-status-and-results), inkludert deres frafallspoengsum og de mest innflytelsesrike funksjonene som har påvirket deres frafallspoengsum.

1. Velg **+ Legg til kunder**.

1. Velg kundene som fungerer som en referanse.

1. Velg **Neste** for å fortsette.

---

### <a name="set-schedule-and-review-configuration"></a>Angi konfigurasjon for planlegging og gjennomgang

1. Angi en hyppighet for gjenopplæring av modellen. Denne innstillingen er viktig for å oppdatere nøyaktigheten til prognoser når nye data hentes inn. De fleste virksomheter kan gjenopplære én gang i måneden og få god nøyaktighet for prognosen.

1. Velg **Neste**.

1. Se gjennom konfigurasjonen av prediksjonen. Du kan gå tilbake til tidligere trinn ved å velge **Rediger** under verdien som vises. Du kan også velge et konfigurasjonstrinn fra fremdriftsindikatoren.

1. Hvis alle verdier er konfigurert på riktig måte, velger du **Lagre og kjør** for å starte forutsigelsesprosessen. I kategorien **Mine prediksjoner** kan du vise statusen for prediksjonene. Det kan ta flere timer før prosessen er fullført, avhengig av mengden data som brukes i forutsigelsen.

## <a name="review-a-prediction-status-and-results"></a>Se gjennom en forutsigelsesstatus og resultater

1. Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.

1. Velg prognosen du vil gå gjennom.
   - **Navn på prediksjon**: Navnet på prediksjonen som ble angitt under opprettingen.
   - **Prediksjontype**: Typen modell som brukes for prediksjonen
   - **Utdataenhet**: Navn på enheten for å lagre utdataene fra prediksjonen. Du kan finne en enhet med dette navnet på **Data** > **Enhteter**.
     I utdataenheten er *ChurnScore* den anslåtte sannsynligheten for frafall, og *IsChurn* er en binær etikett basert på *ChurnScore* med en terskel på 0,5. Standardterskelen fungerer kanskje ikke for scenariet. [Opprett et nytt segment](segments.md#create-a-new-segment) med din foretrukne terskelverdi.
     Ikke alle kunder er nødvendigvis aktive kunder. Noen av dem har kanskje ikke hatt noen aktivitet på lenge og anses som frafalt allerede, basert på din frafallsdefinisjon. Å forutsi frafallsrisiko for kunder som allerede er frafalt, er ikke nyttig fordi de ikke er en interessant målgruppe.
   - **Forespeilet felt**: Dette feltet fylles bare ut for enkelte typer prediksjoner, og brukes ikke i frafallsprediksjon.
   - **Status**: Statusen for prediksjonskjøringen.
        - **I kø**: Prediksjon venter på at andre prosesser skal kjøre.
        - **Oppdaterer**: Prognosen kjører for å produsere resultater som flytes til utdataenheten.
        - **Mislyktes**: Prediksjonskjøringen mislyktes. [Se gjennom loggene](manage-predictions.md#troubleshoot-a-failed-prediction) for mer informasjon.
        - **Fullført**: Prediksjonen ble fullført. Velg **Vis** under de loddrette ellipsene for å gå gjennom forutsigelsen
   - **Redigert**: Datoen da konfigurasjonen av prediksjonen ble endret.
   - **Sist oppdatert**: Datoen da prediksjonen oppdaterte resultater i utdataenheten.

1. Velg de loddrette ellipsene ved siden av den forutsigelsen du vil se gjennom resultatene for, og velg **Vis**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Vise kontroll for å se resultatene av en prediksjon.":::

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

1. Det er tre hoveddeler med data på resultatsiden:
   - **Ytelse for opplæringsmodell**: A, B eller C er mulige resultater. Denne poengsummen angir ytelsen til prediksjonen og kan hjelpe deg med å ta beslutningen om å bruke resultatene som er lagret i utdataenheten. Poengsummer blir fastslått basert på følgende regler: 
        - **A** Når modellen har forutsett nøyaktig minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er større enn grunnlinjen med minst 10 %.
            
        - **B** Når modellen har forutsett nøayktig minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er opptil 10 %større enn grunnlinjen.
            
        - **C** Når modellen har forutsett nøayktig mindre enn 50 % av de totale prognosene, eller når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er mindre enn grunnlinjen.
               
        - **Grunnlinje** tar inndataene i tidsvinduets for prediksjonen for modellen (for eksempel ett år), og modellen oppretter forskjellige fraksjoner av tiden ved å dele den på 2 til den når én måned eller mindre. Den bruker disse brøkene til å opprette en forretningsregel for kunder som ikke har kjøpt i denne tidsrammen. Disse kundene anses som frafalt. Den tidsbaserte forretningsregelen med høyest mulig evne til å forutse hvem som sannsynligvis vil frafalle, velges som grunnlinjemodellen.
            
    - **Sannsynligheten for frafall (antall kunder)**: Grupper av kunder basert på den predikerte risikoen for frafall. Disse dataene kan hjelpe deg senere hvis du vil opprette et segment av kunder med høy frafallsrisiko. Slike segmenter hjelper deg med å forstå hvor grensen bør gå for segmentmedlemskap.
       
    - **Mest innflytelsesrike faktorer**: Det er mange faktorer du må ta hensyn til når du oppretter forutsigelsen. Hver av faktorene har sin viktighet beregnet for de aggregerte prognosene som en modell oppretter. Du kan bruke disse faktorene til å validere resultatene for prediksjon, eller du kan bruke denne informasjonen senere til å [opprette segmenter](segments.md) som kan ha innvirkning på frafallsrisikoen for kundene.


# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

1. Det er tre hoveddeler med data på resultatsiden:
   - **Ytelse for opplæringsmodell**: A, B eller C er mulige resultater. Denne poengsummen angir ytelsen til prediksjonen og kan hjelpe deg med å ta beslutningen om å bruke resultatene som er lagret i utdataenheten. Poengsummer blir fastslått basert på følgende regler: 
        - **A** Når modellen har forutsett nøyaktig minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er større enn grunnlinjen med minst 10 %.
            
        - **B** Når modellen har forutsett nøayktig minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er opptil 10 %større enn grunnlinjen.
            
        - **C** Når modellen har forutsett nøayktig mindre enn 50 % av de totale prognosene, eller når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er mindre enn grunnlinjen.
               
        - **Grunnlinje** tar inndataene i tidsvinduets for prediksjonen for modellen (for eksempel ett år), og modellen oppretter forskjellige fraksjoner av tiden ved å dele den på 2 til den når én måned eller mindre. Den bruker disse brøkene til å opprette en forretningsregel for kunder som ikke har kjøpt i denne tidsrammen. Disse kundene anses som frafalt. Den tidsbaserte forretningsregelen med høyest mulig evne til å forutse hvem som sannsynligvis vil frafalle, velges som grunnlinjemodellen.
            
    - **Sannsynligheten for frafall (antall kunder)**: Grupper av kunder basert på den predikerte risikoen for frafall. Disse dataene kan hjelpe deg senere hvis du vil opprette et segment av kunder med høy frafallsrisiko. Slike segmenter hjelper deg med å forstå hvor grensen bør gå for segmentmedlemskap.
       
    - **Mest innflytelsesrike faktorer**: Det er mange faktorer du må ta hensyn til når du oppretter forutsigelsen. Hver av faktorene har sin viktighet beregnet for de aggregerte prognosene som en modell oppretter. Du kan bruke disse faktorene til å validere resultatene for prediksjon, eller du kan bruke denne informasjonen senere til å [opprette segmenter](segments.md) som kan ha innvirkning på frafallsrisikoen for kundene.


1. For forretningskontoer finner du informasjonssiden **Innflytelsesrik funksjonsanalyse**. Den inneholder fire deler med data:

    - Elementet som er valgt i ruten til høyre, bestemmer innholdet på denne siden. Velg et element fra **De beste kundene** eller **Referansekunder**. Begge listene ordnes ved å redusere verdien av frafallspoengsummen, enten poengsummen er bare for kunden eller en kombinert poengsum for kunder og et sekundært nivå som produktkategori.
        
        - **De beste kundene**: Liste over 10 kunder som har høyest risiko for frafall og lavest risiko for frafall basert på kundens frafallspoengsummer. 
        - **Referansekunder**: Liste over opptil 10 kunder som ble valgt under konfigurasjon av modellen.
 
    - **Frafallspoengsum**: Viser frafallspoengsummen for det valgte elementet i høyre rute.
    
    - **Frafallsrisikofordeling:** Viser frafallsrisikodistribusjonen på tvers av kunder og persentilet som den valgte kunden er i. 
    
    - **Toppfunksjoner som øker eller reduserer frafallsrisiko:** For det valgte elementet i ruten til høyre vises de fem viktigste funksjonene som økte og reduserte frafallsrisikoen. For hver innflytelsesrike funksjon finner du verdien av funksjonen for elementet og dens innflytelse på poengsummen. Den gjennomsnittlige verdien av hver funksjon på tvers av segmenter for lave, middels og høye frafallskundesegmenter vises også. Det bidrar til bedre kontekstualisere verdiene for de mest innflytelsesrike funksjonene for det valgte elementet, og sammenligner det med lave, middels og høye kundesegmenter.

       - Lav: forretningsforbindelser eller kombinasjoner av forretningsforbindelse og sekundært nivå med en frafallspoengsum på mellom 0 og 0,33
       - Middels: forretningsforbindelser eller kombinasjoner av forretningsforbindelser og sekundære nivåer med en frafallspoengsum på mellom 0,33 og 0,66
       - Høy: forretningsforbindelser eller kombinasjoner av forretningsforbindelser og sekundære nivåer med en frafallspoengsum høyere enn 0,66
    
       Når du forutsier frafall på forretningsforbindelsesnivå, vurderes alle forretningsforbindelser ved utlede de gjennomsnittlige funksjonsverdiene for frafallssegmenter. For frafallsprognoser på sekundært nivå for hver forretningsforbindelse avhenger utledingen av frafallssegmenter på sekundært nivå av elementet som er valgt i sideruten. Hvis et element for eksempel har et sekundært produktkategorinivå = kontorrekvisita, vurderes bare elementene som har kontorrekvisita som produktkategorien, når de gjennomsnittlige funksjonsverdiene for frafallssegmenter hentes ut. Denne logikken brukes for å sikre en rettferdig sammenligning av elementets funksjonsverdier med de gjennomsnittlige verdiene på tvers av segmenter med lavt, middels og høyt frafall.

       I noen tilfeller er den gjennomsnittlige verdien av frafallssegmenter med lavt, middels eller høyt nivå, ikke tilgjengelige fordi det ikke finnes elementer som tilhører de tilsvarende frafallssegmentene basert på definisjonen ovenfor.
       
       > [!NOTE]
       > Tolkning av verdier under kolonnene for gjennomsnittlig lav, middels og høy er forskjellig for kategoriske funksjoner som land eller bransje. Ettersom anseelsen om gjennomsnittlig funksjonsverdi ikke gjelder kategoriske funksjoner, er verdiene i disse kolonnene en andel av kundene i segmenter med lavt, middels eller høyt frafall som har samme verdi i den kategoriske funksjonen sammenlignet med elementet som er valgt i sidepanelet.

---

## <a name="manage-predictions"></a>Administrere prediksjoner

Det går an å optimalisere, feilsøke, oppdatere eller slette prognoser. Se gjennom en brukbarhetsrapport for inndata for å finne ut hvordan du gjør en prediksjon raskere og mer pålitelig. Hvis du vil ha mer informasjon, kan du gå til [Administrere prediksjoner](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
