---
title: Frafallsprediksjon for abonnement
description: Du kan forutsi om en kunde er i faresonen for ikke lenger å bruke selskapets abonnementsprodukter eller tjenester.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 9eb0593f93d713124e4113dcb62c588819f5b97b
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556319"
---
# <a name="subscription-churn-prediction-preview"></a>Forutsigelse av abonnementsfrafall (forhåndsversjon)

Forutsigelse av abonnementsfrafall hjelper deg med å forutsi om en kunde er i faresonen for ikke lenger å bruke selskapets abonnementsprodukter eller tjenester. Du kan opprette en ny forutsigelse av abonnementsfrafalla på siden **Inntelligens** > **Prediksjoner**. Velg **Mine prediksjoner** for å se andre prediksjoner du har opprettet.

> [!TIP]
> Prøv opplæringen for en prognose på abonnementsfrafall ved hjelp av eksempeldata: [Eksempelveiledning for prognose på abonnementsfrafall](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Forutsetninger

- Minst [bidragsytertillatelser](permissions.md).
- Forretningskunnskap for å forstå hva frafall betyr for bedriften din. Vi støtter tidsbaserte frafallsdefinisjoner, noe som betyr at en kunde anses å ha frafalt et tidsrom etter at abonnementet er avsluttet.
- Data om abonnementene og deres logg:
    - Abonnements-ID-er for å skille abonnementer.
    - Kunde-ID-er for å samsvare abonnementer på kundene.
    - Dato for abonnementshendelser, som definerer startdatoer, sluttdatoer og datoene da abonnementshendelsene ble utført.
    - Abonnementsinformasjon for å definere om det er et regelmessig abonnement og hvor ofte det blir fornyet.
    - Det semantiske dataskjemaet for abonnementer krever følgende informasjon:
        - **Abonnements-ID:** En unik identifikator for et abonnement.
        - **Sluttdato for abonnement:** Datoen abonnementet utløper for kunden.
        - **Startdato for abonnement:** Datoen abonnementet starter for kunden.
        - **Transaksjonsdato:** Datoen da en abonnementsendring skjedde. For eksempel en kunde som kjøper eller annullerer et abonnement.
        - **Er det et gjentakende abonnement:** Et boolsk sann/usann-felt som avgjør om abonnementet skal fornyes med samme abonnements-ID uten kunde innblanding
        - **Regelmessighetshyppighet (i måneder):** For gjentakende abonnementer er det perioden abonnementet vil fornye. Den vises i måneder. Et årlig abonnement som automatisk fornyer for en kunde hvert år for et nytt år, har for eksempel verdien 12.
        - (Valgfritt) **Abonnementsbeløp:** Valutabeløpet en kunde betaler for fornyelse av abonnementet. Den kan hjelpe deg med å identifisere mønstre for forskjellige abonnementsnivåer.
- Data om kundeaktiviteter:
    - Aktivitets-ID-er for å skille mellom aktiviteter av samme type.
    - Kunde-ID-er for å tilordne aktiviteter til kundene.
    - Aktivitetsinformasjon som inneholder navnet på og datoen for aktiviteten.
    - Det semantiske dataskjemaet for kundeaktiviteter omfatter følgende:
        - **Primærnøkkel:** En unik identifikator for en aktivitet. For eksempel et besøk på et nettsted eller en bruksoppføring som viser at kunden viste et TV-program.
        - **Tidsstempel:** Dato og klokkeslett for hendelsen som er identifisert ved hjelp av primærnøkkelen.
        - **Hendelse:** Navnet på hendelsen du vil bruke. Et felt kalt "UserAction" i en strømmevideotjeneste kan for eksempel ha verdien "Vist".
        - **Detaljer:** Detaljert informasjon om hendelsen. Et felt kalt "ShowTitle" i en strømmevideotjeneste kan for eksempel ha verdien for en video som kunden har sett på.
- Kjennetegn for foreslåtte data:
    - Tilstrekkelige historiske data: Abonnementsdata for minst det dobbelte av det valgte tidsvinduet. Fortrinnsvis to til tre år med abonnementsdata.
    - Abonnementsstatus: Data inkluderer aktive og inaktive abonnementer for hver kunde, slik at det er flere oppføringer per kunde-ID.
    - Antall kunder: Minst 10 kundeprofiler, helst mer enn 1 000 unike kunder. Modellen vil mislykkes med færre enn 10 kunder og utilstrekkelige historiske data.
    - Datafullføring: Mindre enn 20 % av manglende verdier i datafeltet for den angitte enheten.
   
   > [!NOTE]
   > Du må ha minst to aktivitetsoppføringer for 50 % av kundene du vil beregne frafall for.

## <a name="create-a-subscription-churn-prediction"></a>Opprette en forutsigelse av abonnementsfrafall

1. I Målgruppeinnsikt går du til **Intelligens** > **Prognoser**.
1. Velg flisen **Modell for abonnementsfrafall (forhåndsversjon)**, og velg **Bruk denne modellen**.
   > [!div class="mx-imgBorder"]
   > ![Flisen Modell for abonnementsfrafall med knappen Bruk denne modellen.](media/subscription-churn-usethismodel.PNG "Flisen Modell for abonnementsfrafall med knappen Bruk denne modellen")

### <a name="name-model"></a>Gi navn til modell

1. Angi et navn på modellen for å skille den fra andre modeller.
1. Angi et navn for utdataenheten bare ved hjelp av bokstaver og tall, uten mellomrom. Det er navnet som modellenheten vil bruke. Velg deretter **Neste**.

### <a name="define-customer-churn"></a>Definer kundefrafall

1. Angi et antall for **Dager siden abonnement ble avsluttet** som bedriften anser at en kunde er i frafalt tilstand. Denne perioden er vanligvis knyttet til forretningsaktiviteter som tilbud eller andre markedsføringstiltak som prøver å hindre at bedriften mister kunden.
1. Angi antall **dager å se inn i fremtiden for å forutsi frafall** for å angi et vindu å forutsi frafall for. Hvis du for eksempel vil forutsi risikoen for frafall for kundene dine i løpet av de neste 90 dagene, og justere markedsføringstiltak. Å forutsi frafallsrisiko i lengre eller kortere perioder kan gjøre det vanskeligere å håndtere faktorene i profilen for frafallsrisiko, avhengig av dine spesielle forretningskrav. Velg **Neste** for å fortsette
   >[!TIP]
   > Du kan velge **Lagre og lukk** når som helst for å lagre forutsigelsen som et utkast. Du finner utkastforutsigelsen i **Mine prediksjoner**-fanen for å fortsette.

### <a name="add-required-data"></a>Legg til obligatoriske data

1. Velg **Legg til data** for **Abonnementslogg**, og velg enheten som inneholder informasjon om abonnementsloggen, slik det er beskrevet i [forhåndskravene](#prerequisites).
1. Hvis feltene nedenfor ikke fylles ut, konfigurerer du relasjonen fra enheten for abonnementslogg til kundeenheten.
    1. Velg **Enhet for abonnementslogg**.
    1. Velg **feltet** som identifiserer kunden i enheten for abonnementslogg. Det må relateres til den primære kunde-ID-en til kundeenheten.
    1. Velg **kundeenheten** som samsvarer med den primære kundeenheten.
    1. Angi et navn som beskriver relasjonen.
       > [!div class="mx-imgBorder"]
       > ![Siden for abonnementslogg med opprettelse av en relasjon til kunden.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Siden for abonnementslogg med opprettelse av en relasjon til kunden")
1. Velg **Neste**.
1. Tilordne de semantiske feltene til attributter i enheten for abonnementslogg, og velg **Lagre**. Hvis du vil ha beskrivelser av feltene, kan du se på [forhåndskravene](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Siden med abonnementslogg som viser semantiske attributter som er tilordnet til felt i den valgte enheten for abonnementslogg.](media/subscription-churn-subscriptionhistorymapping.PNG "Siden med abonnementslogg som viser semantiske attributter som er tilordnet til felt i den valgte enheten for abonnementslogg")
1. Velg **Legg til data** for **Kundeaktiviteter**, og velg enheten som inneholder informasjon om kundeaktiviteten, slik det er beskrevet i forhåndskravene.
1. Velg en aktivitetstype som samsvarer med typen kundeaktivitet du skal konfigurere.  Velg **Opprett ny**, og angi et navn hvis du ikke ser et alternativ som samsvarer med aktivitetstypen du trenger.
1. Du må konfigurere relasjonen fra kundeaktivitetsenheten til kundeenheten.
    1. Velg feltet som identifiserer kunden i tabellen over kundeaktivitet, som kan være direkte relatert til den primære kunde-ID-en til kundeenheten.
    1. Velg kundeenheten som samsvarer med den primære kundeenheten.
    1. Angi et navn som beskriver relasjonen.
1. Velg **Neste**.
1. Tilordne de semantiske feltene til attributter i kundeaktivitetsenheten, og velg **Lagre**. Hvis du vil ha beskrivelser av feltene, kan du se på [forhåndskravene](#prerequisites).
1. (Valgfritt) Hvis du har andre kundeaktiviteter som du vil ha med, gjentar du fremgangsmåten ovenfor.
   > [!div class="mx-imgBorder"]
   > ![Definer enhetsrelasjonen.](media/subscription-churn-customeractivitiesmapping.PNG "Siden med kundeaktiviteter som viser semantiske attributter som er tilordnet til felt i den valgte enheten for kundeaktivitet")
1. Velg **Neste**.

### <a name="set-schedule-and-review-configuration"></a>Angi konfigurasjon for planlegging og gjennomgang

1. Angi en hyppighet for gjenopplæring av modellen. Denne innstillingen er viktig for å oppdatere nøyaktigheten til prognoser når nye data hentes inn i målgruppeinnsikt. De fleste virksomheter kan gjenopplære én gang i måneden og få god nøyaktighet for prognosen.
1. Velg **Neste**.
1. Se gjennom konfigurasjonen. Du kan gå tilbake til en hvilken som helst del av forutsigelseskonfigurasjonen ved å velge **Rediger** under verdien som vises. Du kan også velge et konfigurasjonstrinn fra fremdriftsindikatoren.
1. Hvis alle verdier er konfigurert på riktig måte, velger du **Lagre og kjør** for å starte forutsigelsesprosessen. I kategorien **Mine prediksjoner** kan du vise statusen for prediksjonene. Det kan ta flere timer før prosessen er fullført, avhengig av mengden data som brukes i forutsigelsen.

## <a name="review-a-prediction-status-and-results"></a>Se gjennom en forutsigelsesstatus og resultater

1. Gå til kategorien **Mine prediksjoner** i **Intelligens** > **Prediksjoner**.
   > [!div class="mx-imgBorder"]
   > ![Visning av Mine prediksjoner-siden.](media/subscription-churn-mypredictions.PNG "Visning av Mine prediksjoner-siden")
1. Velg prognosen du vil gå gjennom.
   - **Navn på prediksjon:** Navnet på prediksjonen som ble angitt under opprettingen.
   - **Prediksjonstype:** Typen modell som brukes for prediksjonen.
   - **Utdataenhet:** Navn på enheten for å lagre utdataene fra prediksjonen. Du kan finne en enhet med dette navnet på **Data** > **Enhteter**.    
     I utdataenheten er *ChurnScore* den anslåtte sannsynligheten for frafall, og *IsChurn* er en binær etikett basert på *ChurnScore* med en terskel på 0,5. Standardterskelen fungerer kanskje ikke for scenariet. [Opprett et nytt segment](segments.md#create-a-new-segment) med din foretrukne terskelverdi.
   - **Forespeilet felt:** Dette feltet fylles bare ut for enkelte typer prediksjoner, og brukes ikke i forutsigelse av abonnementsfrafall.
   - **Status:** Gjeldende status for prediksjonskjøringen.
        - **I kø:** Forutsigelsen venter på at andre prosesser kjøres.
        - **Oppdaterer:** Forutsigelsen kjører for øyeblikket "poengsum"-trinnet i behandlingen for å gi resultatene som flyter til utdataenheten.
        - **Mislyktes:** Forutsigelsen mislyktes. Velg **Logger** hvis du vil ha mer informasjon.
        - **Vellykket:** Forutsigelsen var vellykket. Velg **Vis** under de loddrette ellipsene for å gå gjennom forutsigelsen
   - **Redigert:** Datoen da konfigurasjonen av forutsigelsen ble endret.
   - **Sist oppdatert:** Datoen da forutsigelsen oppdaterte resultater i utdataenheten.
1. Velg de loddrette ellipsene ved siden av den forutsigelsen du vil se gjennom resultatene for, og velg **Vis**.
   > [!div class="mx-imgBorder"]
   > ![Visning av alternativer på loddrette ellipser-menyen for en forutsigelse, blant annet rediger, oppdater, vis, logger og slett.](media/subscription-churn-verticalellipses.PNG "Visning av alternativer på loddrette ellipser-menyen for en forutsigelse, blant annet rediger, oppdater, vis, logger og slett")
1. Det er tre hoveddeler med data på resultatsiden:
    1. **Ytelse for opplæringsmodell:** A, B eller C er mulige resultater. Denne poengsummen angir ytelsen til forutsigelsen, og kan hjelpe deg med å ta beslutningen om å bruke resultatene som er lagret i utdataenheten.
        - Poengsummer blir fastslått basert på følgende regler:
            - **A** når modellen har forutsagt minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som er frafalt, er større enn den historiske gjennomsnittlige frafallsfrekvensen med minst 10 % av den historiske gjennomsnittlige frafallsfrekvensen.
            - **B** når modellen har forutsagt minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som er frafalt, er opptil 10 % større enn den historiske gjennomsnittlige frafallsfrekvensen for den historiske gjennomsnittlige frafallsfrekvensen.
            - **C** når modellen nøyaktig har forutsagt mindre enn 50 % av de totale prognoser, eller når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er mindre enn den historiske gjennomsnittlige frafallsfrekvensen.
               > [!div class="mx-imgBorder"]
               > ![Visning av modellytelsesresultatet.](media/subscription-churn-modelperformance.PNG "Visning av modellytelsesresultatet")
    1. **Sannsynligheten for frafall (antall kunder):** Grupper av kunder basert på den predikerte risikoen for frafall. Disse dataene kan hjelpe deg senere hvis du vil opprette et segment av kunder med høy frafallsrisiko. Slike segmenter hjelper deg med å forstå hvor grensen bør gå for segmentmedlemskap.
       > [!div class="mx-imgBorder"]
       > ![Diagram som viser fordeling av frafallsresultater, delt opp i områder fra 0 til 100 %.](media/subscription-churn-resultdistribution.PNG "Diagram som viser fordeling av frafallsresultater, delt opp i områder fra 0 til 100 %")
    1. **Mest innflytelsesrike faktorer:** Det er mange faktorer du må ta hensyn til når du oppretter forutsigelsen. Hver av faktorene har sin viktighet beregnet for de aggregerte prognoser som opprettes av en modell. Du kan bruke disse faktorene til å validere forutsigelsesresultatene. Du kan også bruke denne informasjonen senere til å [opprette segmenter](segments.md) som kan ha innvirkning på frafallsrisiko for kunder.
       > [!div class="mx-imgBorder"]
       > ![Liste med innflytelsesrike faktorer og viktigheten av dem, for å forutsi frafallsresultatet.](media/subscription-churn-influentialfactors.PNG "Liste med innflytelsesrike faktorer og viktigheten av dem, for å forutsi frafallsresultatet")

## <a name="manage-predictions"></a>Administrere prediksjoner

Det går an å optimalisere, feilsøke, oppdatere eller slette prognoser. Se gjennom en brukbarhetsrapport for inndata for å finne ut hvordan du gjør en prediksjon raskere og mer pålitelig. Hvis du vil ha mer informasjon, kan du se [Administrere prediksjoner](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
