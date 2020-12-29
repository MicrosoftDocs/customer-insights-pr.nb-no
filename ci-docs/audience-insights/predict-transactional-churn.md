---
title: Transaksjonell frafallsprognose
description: Forutsi om en kunde er i faresonen for ikke lenger å kjøpe produktene eller tjenestene dine.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f3cbbf99a6cecba2aab2cf85428d53e5df8346e4
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644415"
---
# <a name="transactional-churn-prediction-preview"></a>Transaksjonell frafallsprognose (forhåndsversjon)

Transaksjonsell frafallsprognose bidrar til å forutse om en kunde ikke lenger kjøper produktene eller tjenestene dine i et gitt tidsvindu. Du kan opprette nye frafallsprognoser under **Intelligens** > **Prognoser**. Velg **Mine prediksjoner** for å se andre prediksjoner du har opprettet.

> [!TIP]
> Prøv opplæringen for en transaksjonsll frafallsprognose ved hjelp av eksempeldata: [Eksempelveiledning for transaksjonell frafallsprognose (forhåndsversjon)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Forutsetninger

- Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.
- Forretningskunnskap for å forstå hva frafall betyr for bedriften din. Vi støtter tidsbaserte frafallsdefinisjoner, som betyr at en kunde anses å ha frafalt etter en periode der det ikke er kjøp.
- Data om dine transaksjoner/kjøp og deres historikk:
    - Transaksjons-ID-er for å skille innkjøp/transaksjoner.
    - Kunde-ID-er for å samsvare transaksjoner for kundene.
    - Dato for transaksjonshendelser, som definerer datoene da transaksjonen forekom.
    - Det semantiske dataskjemaet for kjøp/transaksjoner krever følgende informasjon:
        - **Transaksjons-ID:** En unik identifikator for et innkjøp eller en transaksjon.
        - **Transaksjonsdato:** Datoen for innkjøpet eller transaksjonen.
        - **Verdien av transaksjonen:** Valutabeløpet / det numeriske verdibeløpet for transaksjonen/varen.
        - (Valgfritt) **Unik produkt-ID:** ID-en til produktet eller tjenesten som er kjøpt, hvis dataene er på et linjevarenivå.
        - (Valgfritt) **Om denne transaksjonen var en tilbakeføring:** Et sant/usant-felt som registrerer om transaksjonen var en retur eller ikke. Hvis **Verdien av transaksjonen** er negativ, vil vi også bruke denne informasjonen til å utlede en retur.
- (Valgfritt) Data om kundeaktiviteter:
    - Aktivitets-ID-er for å skille mellom aktiviteter av samme type.
    - Kunde-ID-er for å tilordne aktiviteter til kundene.
    - Aktivitetsinformasjon som inneholder navnet på og datoen for aktiviteten.
    - Det semantiske dataskjemaet for kundeaktiviteter omfatter følgende:
        - **Primærnøkkel:** En unik identifikator for en aktivitet. Et besøk på et nettsted eller en bruksoppføring som for eksempel viser at kunden prøvde et prøveeksemplar av produktet ditt.
        - **Tidsstempel:** Dato og klokkeslett for hendelsen som er identifisert ved hjelp av primærnøkkelen.
        - **Hendelse:** Navnet på hendelsen du vil bruke. Et felt kalt "Brukerhandling" i en dagligvareforretning kan for eksempel være en kupong som brukes av kunden.
        - **Detaljer:** Detaljert informasjon om hendelsen. Et felt kalt "Kupongverdi" i et dagligvareforretning kan for eksempel være valutaverdien for kupongen.

## <a name="create-a-transactional-churn-prediction"></a>Opprette en transaksjonell frafallsprognose

1. Gå til **Intelligens** > **Prognoser** i Customer Insights.

1. Velg flisen **Modell for kundefrafall (forhåndsversjon)**, og velg **Bruk denne modellen**.
   
1. I ruten **Modell for kundefrafall** velger du **Transaksjonell** og velger **Kom i gang**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Skjermbilde med valgt transaksjonsalternativ i ruten Modell for kundefrafall.":::

### <a name="name-model"></a>Gi navn til modell

1. Angi et navn på modellen for å skille den fra andre modeller.

1. Angi et navn for utdataenheten bare ved hjelp av bokstaver og tall, uten mellomrom. Det er navnet som modellenheten vil bruke. 

1. Velg **Neste**.

### <a name="define-customer-churn"></a>Definer kundefrafall

1. Angi et vindu med dager for å forutse frafall i feltet **Identifiser kunder som kan frafalle de neste**. Du kan for eksempel forutse risikoen for frafall for kundene dine i løpet av de neste 90 dagene, for å rette inn tiltak for å beholde kundene i markedsføringen. Å forutse frafallsrisiko for en lengre eller kortere tidsperiode kan gjøre det vanskeligere å håndtere faktorene i din frafallsrisikoprofil, men det avhenger av dine spesifikke forretningskrav. 
   >[!TIP]
   > Du kan velge **Lagre og lukk** når som helst for å lagre forutsigelsen som et utkast. Du finner utkastforutsigelsen i **Mine prediksjoner**-fanen for å fortsette.

1. Angi hvor mange dager det skal defineres frafall, i feltet **En kunde har frafalt hvis de ikke har foretatt noen kjøp på**. Hvis for eksempel en kunde ikke har gjort noen kjøp i løpet av de siste 30 dagene, kan de anses som frafalt for bedriften din. 

1. Velg **Neste** for å fortsette

### <a name="add-required-data"></a>Legg til obligatoriske data

1. Velg **Legg til data** for **Kjøpshistorikk**, og velg enheten som inneholder informasjon om transaksjons-/kjøpshistorikken, slik dette er beskrevet i [forhåndskravene](#prerequisites).

1. Tilordne de semantiske feltene til attributter i kjøpsloggenheten, og velg deretter **Neste**. Hvis du vil ha beskrivelser av feltene, kan du se på [forhåndskravene](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Tilordne semantiske felt for kjøpsenheten.":::

1. Hvis feltene nedenfor ikke fylles ut, konfigurerer du relasjonen fra kjøpsloggenheten til kundeenheten.
    1. Velg **Kjøpshistorikkenhet**.
    1. Velg **feltet** som identifiserer kunden i kjøpshistorikkenheten. Det må relateres til den primære kunde-ID-en til kundeenheten.
    1. Velg **kundeenheten** som samsvarer med den primære kundeenheten.
    1. Angi et navn som beskriver relasjonen.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Side med kjøpshistorikk som viser opprettelsen av en relasjon til kunde.":::
   
1. Velg **Neste**.

1. Du kan eventuelt velge **Legg til data** for **Kundeaktiviteter**. Velg enheten som inneholder informasjon om kundeaktiviteten, slik det er beskrevet i forhåndskravene.

1. Tilordne de semantiske feltene til attributter i kundeaktivitetsenheten, og velg deretter **Neste**. Hvis du vil ha beskrivelser av feltene, kan du se på [forhåndskravene](#prerequisites).

1. Velg en aktivitetstype som samsvarer med typen kundeaktivitet du skal konfigurere. Velg **Opprett ny**, og velg en tilgjengelig aktivitetstype, eller opprett en ny type.

1. Du må konfigurere relasjonen fra kundeaktivitetsenheten til kundeenheten.
    1. Velg feltet som identifiserer kunden i kundeaktivitetstabellen. Den kan være direkte relatert til den primære kunde-ID-en til kundeenheten.
    1. Velg kundeenheten som samsvarer med den primære kundeenheten.
    1. Angi et navn som beskriver relasjonen.

1. Velg **Lagre**.

1. Hvis du har andre kundeaktiviteter som du vil ha med, gjentar du fremgangsmåten ovenfor.

1. Velg **Neste**.

### <a name="set-schedule-and-review-configuration"></a>Angi konfigurasjon for planlegging og gjennomgang

1. Angi en hyppighet for gjenopplæring av modellen. Denne innstillingen er viktig for å oppdatere nøyaktigheten til prognoser når nye data hentes inn. De fleste virksomheter kan gjenopplære én gang i måneden og få god nøyaktighet for prognosen.

1. Velg **Neste**.

1. Se gjennom konfigurasjonen av prediksjonen. Du kan gå tilbake til tidligere trinn ved å velge **Rediger** under verdien som vises. Du kan også velge et konfigurasjonstrinn fra fremdriftsindikatoren.

1. Hvis alle verdier er konfigurert på riktig måte, velger du **Lagre og kjør** for å starte forutsigelsesprosessen. I kategorien **Mine prediksjoner** kan du vise statusen for prediksjonene. Det kan ta flere timer før prosessen er fullført, avhengig av mengden data som brukes i forutsigelsen.

## <a name="review-a-prediction-status-and-results"></a>Se gjennom en forutsigelsesstatus og resultater

1. Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.

1. Velg prognosen du vil gå gjennom.
   - **Navn på prediksjon:** Navnet på prediksjonen som ble angitt under opprettingen.
   - **Prediksjontype:** Typen modell som brukes for prediksjonen.
   - **Utdataenhet:** Navn på enheten for å lagre utdataene fra prediksjonen. Du kan finne en enhet med dette navnet på **Data** > **Enhteter**.
   - **Forespeilet felt:** Dette feltet fylles bare ut for enkelte typer prediksjoner, og brukes ikke i frafallsprediksjon.
   - **Status:** Statusen for prognosekjøringen.
        - **I kø:** Prognonsen venter på at andre prosesser skal kjøre.
        - **Oppdaterer:** Prognosen kjører for å produsere resultater som flytes til utdataenheten.
        - **Mislyktes:** Prognosekjøringen mislyktes. [Se gjennom loggene](#troubleshoot-a-failed-prediction) for mer informasjon.
        - **Fullført:** Prognosen ble fullført. Velg **Vis** under de loddrette ellipsene for å gå gjennom forutsigelsen
   - **Redigert:** Datoen da konfigurasjonen av forutsigelsen ble endret.
   - **Sist oppdatert:** Datoen da forutsigelsen oppdaterte resultater i utdataenheten.

1. Velg de loddrette ellipsene ved siden av den forutsigelsen du vil se gjennom resultatene for, og velg **Vis**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Vise kontroll for å se resultatene av en prediksjon.":::   

1. Det er tre hoveddeler med data på resultatsiden:
    1. **Ytelse for opplæringsmodell:** A, B eller C er mulige resultater. Denne poengsummen angir ytelsen til forutsigelsen, og kan hjelpe deg med å ta beslutningen om å bruke resultatene som er lagret i utdataenheten. Poengsummer blir fastslått basert på følgende regler:
         
         - **A** Når modellen har forutsett nøyaktig minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er større enn grunnlinjen med minst 10 %.
            
         - **B** Når modellen har forutsett nøayktig minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er opptil 10 %større enn grunnlinjen.
            
         - **C** Når modellen har forutsett nøayktig mindre enn 50 % av de totale prognosene, eller når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er mindre enn grunnlinjen.
               
         - **Grunnlinjen** tar inndataene i tidsvinduets for prognosen for modellen (for eksempel ett år), og modellen oppretter forskjellige deler av tiden ved å dele den på 2 til den når én måned eller mindre. Den bruker disse brøkene til å opprette en forretningsregel for kunder som ikke har kjøpt i denne tidsrammen. Disse kundene anses som frafalt. Den tidsbaserte forretningsregelen med høyest mulig evne til å forutse hvem som sannsynligvis vil frafalle, velges som grunnlinjemodellen.
            
    1. **Sannsynligheten for frafall (antall kunder):** Grupper av kunder basert på den predikerte risikoen for frafall. Disse dataene kan hjelpe deg senere hvis du vil opprette et segment av kunder med høy frafallsrisiko. Slike segmenter hjelper deg med å forstå hvor grensen bør gå for segmentmedlemskap.
       
    1. **Mest innflytelsesrike faktorer:** Det er mange faktorer du må ta hensyn til når du oppretter forutsigelsen. Hver av faktorene har sin viktighet beregnet for de aggregerte prognosene som en modell oppretter. Du kan bruke disse faktorene til å validere forutsigelsesresultatene. Du kan også bruke denne informasjonen senere til å [opprette segmenter](segments.md) som kan ha innvirkning på frafallsrisiko for kunder.

## <a name="troubleshoot-a-failed-prediction"></a>Feilsøke en mislykket prognose

1. Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.

1. Velg de loddrette ellipsene ved siden av prediksjonen du vil vise feillogger for.

1. Velg **Logger**.

1. Se gjennom alle feilene. Det finnes flere typer feil som kan oppstå, og de beskriver hvilken betingelse som forårsaket feilen. En feil på grunn av at det ikke er nok data til å forutsi nøyaktig, blir vanligvis løst ved å laste inn flere data i Customer Insights.

## <a name="refresh-a-prediction"></a>Oppdatere en prediksjon

Prognoser oppdateres automatisk på samme [tidsplan som dataene dine oppdateres](system.md#schedule-tab), som konfigurert i innstillingene. Du kan også oppdatere dem manuelt.

1. Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.

1. Velg de loddrette ellipsene ved siden av den forutsigelsen du vil oppdatere.

1. Velg **Oppdater**.

## <a name="delete-a-prediction"></a>Slette en prediksjon

Sletting av en prognose fjerner også utdataenheten.

1. Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.

1. Velg de loddrette ellipsene ved siden av den forutsigelsen du vil slette.

1. Velg **Slett**.
