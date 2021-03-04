---
title: Produktanbefalingsprediksjon
description: Forutsi produktene en kunde sannsynligvis kommer til å kjøpe eller samhandle med.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270519"
---
# <a name="product-recommendation-prediction-preview"></a>Produktanbefalingsprediksjon (forhåndsversjon)

Produktanbefalingsmodellen oppretter sett med prediktive produktanbefalinger. Anbefalingene er basert på tidligere kjøpsatferd og kunder med lignende kjøpsmønstre. Du kan opprette nye produktanbefalingsprediksjoner på siden **Intelligens** > **Prediksjoner**. Velg **Mine prediksjoner** for å se andre prediksjoner du har opprettet.

Produktanbefalinger kan være underlagt lokale lover og forskrifter samt kundens forventninger, som modellen ikke er bygget for spesifikt å ta hensyn til.  Som bruker av denne prediktive funksjonen **må du gjennomgå anbefalingene før du leverer dem til kundene**, for å sikre at du overholder gjeldende lover eller forskrifter samt kundens forventninger til det du kan anbefale. 

I tillegg gir utdataene for denne modellen anbefalinger basert på produkt-ID-en. Leveringsmekanismen må ta beregnede produkt-ID-er og tilordne dem til riktig innhold for kundene slik at de kan ta hensyn til lokalisering, bildeinnhold og annet bestemt innhold eller annen bestmet virkemåte for selskapet.

## <a name="sample-guide"></a>Eksempelveiledning

Hvis du er interessert i å prøve denne funksjonen, men ikke har data for å fullføre kravene nedenfor, kan du [opprette en eksempelimplementering](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Forutsetninger

- Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.
- Forretningskunnskap for å forstå ulike typer produkter for virksomheten og hvordan kundene samhandler med dem. Vi støtter anbefalte produkter som tidligere er kjøpt av kundene dine, eller anbefalinger for nye produkter.
- Data om transaksjoner, kjøp og deres historikk:
    - Transaksjons-ID-er for å skille innkjøp eller transaksjoner.
    - Kunde-ID-er for å tilordne transaksjoner for kundene.
    - Dato for transaksjonshendelser som definerer datoene da transaksjonen forekom.
    - (Valgfritt) Produkt-ID-informasjon for transaksjonen.
    - (Valgfritt) Om en transaksjon er en retur eller ikke.
    - Det semantiske dataskjemaet for kjøp eller transaksjoner krever følgende informasjon:
        - **Transaksjons-ID:** En unik identifikator for et innkjøp eller en transaksjon.
        - **Transaksjonsdato:** Datoen for innkjøpet eller transaksjonen.
        - **Verdien av transaksjonen:** Det numeriske verdibeløpet for kjøpet eller transaksjonen.
        - **Unik produkt-ID:** ID-en til produktet eller tjenesten som er kjøpt, hvis dataene er på et linjevarenivå.
        - (Valgfritt) **Kjøp eller retur:** Et sant/usant-felt som registrerer om transaksjonen var en retur eller ikke. Hvis **Verdien av transaksjonen** er negativ, vil vi også bruke denne informasjonen til å utlede en retur.


## <a name="create-a-product-recommendation-prediction"></a>Opprett en produktanbefalingsprediksjon

1. Gå til **Intelligens** > **Prognoser** i Customer Insights.

1. Velg flisen **Produktanbefalingsmodell (forhåndsversjon)**, og velg **Bruk denne modellen**.
   > [!div class="mx-imgBorder"]
   > ![Flisen Produktanbefalingsmodell med Bruk denne modellen-knappen](media/product-recommendation-usethismodel.PNG "Flisen Produktanbefalingsmodell med Bruk denne modellen-knappen")

1. Se gjennom informasjonen om modellkravene. Hvis du har de nødvendige dataene, velger du **Start**.

### <a name="name-model"></a>Gi navn til modell

1. Angi et navn på modellen for å skille den fra andre modeller.

1. Angi et navn for utdataenheten bare ved hjelp av bokstaver og tall, uten mellomrom. Det er navnet som modellenheten vil bruke. Velg deretter **Neste**.

### <a name="define-product-recommendation-configuration"></a>Definer produktanbefalingskonfigurasjon

1. Angi **antall produkter** du vil anbefale til en kunde. Denne verdien avhenger av hvordan leveringsmåten fyller ut data. Hvis du kan anbefale tre produkter, angir du denne verdien i henhold til dette.
   
   >[!TIP]
   > Du kan velge **Lagre og lukk** når som helst for å lagre forutsigelsen som et utkast. Du finner utkastprediksjonen på fanen **Mine prediksjoner**.

1. Velg om du vil **Foreslå produkter som kunder nylig har kjøpt**.

1. Hvis du har valgt *ikke* å anbefale nylig innkjøpte produkter, angir du vinduet **Se tilbake**. Denne innstillingen angir tidsrammen modellen vurderer før du anbefaler produktet på nytt til brukeren. Angi for eksempel at en kunde kjøper en bærbar datamaskin annenhvert år. Dette vinduet ser på kjøpshistorikken for de siste to årene, og hvis de finner et element, filtreres elementet fra anbefalingene.

1. Velg **Neste**

### <a name="add-required-data"></a>Legg til obligatoriske data

1. Velg **Legg til data** for **Historikk for kundetransaksjon**, og velg enheten som inneholder informasjon om transaksjons-/kjøpshistorikken, slik dette er beskrevet i [forhåndskravene](#prerequisites).

1. Tilordne de semantiske feltene til attributter i kjøpsloggenheten, og velg deretter **Neste**. Hvis du vil ha beskrivelser av feltene, kan du se på [forhåndskravene](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definere enhetsrelasjonen](media/product-recommendation-purchasehistorymapping.PNG "Kjøpshistorikkside som viser semantiske attributter som er tilordnet til felter i den valgte kjøpshistorikkenheten")

1. Hvis feltene nedenfor ikke er fylt ut, konfigurerer du relasjonen fra kjøpsloggenheten til *kundeenheten*.
    1. Velg **Kjøpshistorikkenhet**.
    1. Velg **feltet** som identifiserer kunden i kjøpshistorikkenheten. Det må relateres til den primære kunde-ID-en til *kundeenheten*.
    1. Velg **kundeenheten** som samsvarer med den primære kundeenheten.
    1. Angi et navn som beskriver relasjonen.
       > [!div class="mx-imgBorder"]
       > ![Side med kjøpshistorikk som viser opprettelsen av en relasjon til kunde](media/model-purchase-join.png "Side med kjøpshistorikk som viser opprettelsen av en relasjon til kunde")

1. Velg **Lagre**.

1. Velg **Neste**.

### <a name="set-schedule-and-review-configuration"></a>Angi konfigurasjon for planlegging og gjennomgang

1. Angi en hyppighet for gjenopplæring av modellen. Denne innstillingen er viktig for å oppdatere nøyaktigheten til prognoser når nye data importeres til Customer Insights. De fleste virksomheter kan gjenopplære én gang i måneden og få god nøyaktighet for prognosen.

1. Velg **Neste**.

1. Se gjennom konfigurasjonen. Du kan gå tilbake til en hvilken som helst del av forutsigelseskonfigurasjonen ved å velge **Rediger** under verdien som vises. Du kan også velge et konfigurasjonstrinn fra fremdriftsindikatoren.

1. Hvis alle verdier er konfigurert på riktig måte, velger du **Lagre og kjør** for å starte forutsigelsesprosessen. I kategorien **Mine prediksjoner** kan du vise statusen for prediksjonene. Det kan ta flere timer før prosessen er fullført, avhengig av mengden data som brukes i forutsigelsen.

## <a name="review-a-prediction-status-and-results"></a>Se gjennom en forutsigelsesstatus og resultater

1. Gå til kategorien **Mine prediksjoner** i **Intelligens** > **Prediksjoner**.
   > [!div class="mx-imgBorder"]
   > ![Visning av Mine prediksjoner-siden](media/product-recommendation-mypredictions.PNG "Visning av Mine prediksjoner-siden")

1. Velg prognosen du vil gå gjennom.
   - **Navn på prediksjon:** Navnet på prediksjonen som ble angitt under opprettingen.
   - **Prediksjonstype:** Typen modell som brukes for prediksjonen.
   - **Utdataenhet:** Navn på enheten for å lagre utdataene fra prediksjonen. Du kan finne en enhet med dette navnet på **Data** > **Enhteter**.
   - **Forespeilet felt:** Dette feltet fylles bare ut for enkelte typer prediksjoner, og brukes ikke i frafallsprediksjon.
   - **Status:** Gjeldende status for prediksjonskjøringen.
        - **I kø:** Forutsigelsen venter på at andre prosesser kjøres.
        - **Oppdaterer:** Forutsigelsen kjører for øyeblikket "poengsum"-trinnet i behandlingen for å gi resultatene som flyter til utdataenheten.
        - **Mislyktes:** Forutsigelsen mislyktes. Velg **Logger** hvis du vil ha mer informasjon.
        - **Vellykket:** Forutsigelsen var vellykket. Velg **Vis** under de loddrette ellipsene for å gå gjennom forutsigelsen
   - **Redigert:** Datoen da konfigurasjonen av forutsigelsen ble endret.
   - **Sist oppdatert:** Datoen da forutsigelsen oppdaterte resultater i utdataenheten.

1. Velg de loddrette ellipsene ved siden av den forutsigelsen du vil se gjennom resultatene for, og velg **Vis**.
   > [!div class="mx-imgBorder"]
   > ![Visning av alternativer på loddrette ellipser-menyen for en forutsigelse, blant annet rediger, oppdater, vis, logger og slett](media/product-recommendation-verticalellipses.PNG "Visning av alternativer på loddrette ellipser-menyen for en forutsigelse, blant annet rediger, oppdater, vis, logger og slett")

1. Det er tre hoveddeler med data på resultatsiden:
    1. **Ytelse for opplæringsmodell:** A, B eller C er mulige resultater. Denne poengsummen angir ytelsen til forutsigelsen, og kan hjelpe deg med å ta beslutningen om å bruke resultatene som er lagret i utdataenheten.
        - Poengsummer blir fastslått basert på følgende regler:
            - **A** Modellen blir betraktet som **A**-kvalitet hvis måleverdien Suksess ved K er minst 10 % mer enn basisen. 
            - **B** Modellen blir betraktet som **B**-kvalitet hvis måleverdien Suksess ved K er minst 0 til 10 % mer enn basisen.
            - **C** Modellen blir betraktet som **C**-kvalitet hvis måleverdien Suksess ved K er mindre enn basisen.
               
               > [!div class="mx-imgBorder"]
               > ![Visning av modellytelsesresultatet](media/product-recommendation-modelperformance.PNG "Visning av modellytelsesresultatet")
            - **Basis**: Modellen tar de mest anbefalte produktene etter kjøpsantall for alle kunder, og bruker lærte regler som identifiseres av modellen, til å opprette et sett med anbefalinger for kundene. Prediksjonene sammenlignes deretter med de mest populære produktene basert på antall kunder som hadde kjøpt produktet. Hvis en kunde har minst ett produkt i de anbefalte produktene som også ble sett blant de mest kjøpte produktene, regnes disse som en del av basisen. Hvis det var ti av disse kundene som hadde et anbefalt produkt kjøpt av 100 kunder totalt, ville den opprinnelige basisen vært 10 %.
            - **Suksess ved K**: Ved hjelp av et valideringssett med tidsperioder for transaksjoner opprettes anbefalinger for alle kunder og sammenlignes med valideringssettet for transaksjoner. I en periode på 12 måneder kan for eksempel 12 måneder settes til side som et valideringssett med data. Hvis modellen forutsier minst én ting du ville kjøpt i måned 12, basert på hva den har lært av de forrige 11 månedene, vil kunden øke måleverdien Suksess ved K.
    
    1. **De fleste foreslåtte produktene (med oversikt)**: De fem mest populære produktene som ble forutsett for kundene.
       > [!div class="mx-imgBorder"]
       > ![Diagram som viser de fem mest anbefalte produktene](media/product-recommendation-topproducts.PNG "Diagram som viser de fem mest anbefalte produktene")
    
    1. **Produktanbefalinger med høy sikkerhet**: Et eksempel på anbefalinger gitt til kundene som modellen tror det er sannsynlig at kunden vil kjøpe.
       > [!div class="mx-imgBorder"]
       > ![Liste som viser forslag med høy sikkerhet for et utvalgt sett med individuelle kunder](media/product-recommendation-highconfidence.PNG "Liste som viser forslag med høy sikkerhet for et utvalgt sett med individuelle kunder")

## <a name="fix-a-failed-prediction"></a>Rette en mislykket forutsigelse

1. Gå til kategorien **Mine prediksjoner** i **Intelligens** > **Prediksjoner**.

1. Velg hvilken forutsigelse du vil vise feillogger for, og velg **Logger**.

1. Se gjennom alle feilene. Det finnes flere typer feil som kan oppstå, og de beskriver hvilken betingelse som forårsaket feilen. En feil på grunn av at det ikke er nok data til å forutsi nøyaktig, blir vanligvis løst ved å laste inn flere data i Customer Insights.

## <a name="refresh-a-prediction"></a>Oppdatere en prediksjon

Prediksjoner oppdateres automatisk i den samme [tidsplanen dataene oppdateres](system.md#schedule-tab) som konfigurert i innstillingene.

1. Gå til kategorien **Mine prediksjoner** i **Intelligens** > **Prediksjoner**.

1. Velg de loddrette ellipsene ved siden av den forutsigelsen du vil oppdatere.

1. Velg **Oppdater**.

## <a name="delete-a-prediction"></a>Slette en prediksjon

Sletting av en preiksjon vil også fjerne utdataenheten.

1. Gå til kategorien **Mine prediksjoner** i **Intelligens** > **Prediksjoner**.

1. Velg de loddrette ellipsene ved siden av den forutsigelsen du vil slette.

1. Velg **Slett**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]