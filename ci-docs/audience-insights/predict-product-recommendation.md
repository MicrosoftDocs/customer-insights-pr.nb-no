---
title: Produktanbefalingsprediksjon
description: Forutsi produktene en kunde sannsynligvis kommer til å kjøpe eller samhandle med.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: b9a9c7eb4ee3f2f0510a609757a36e5d5796a2f7
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355763"
---
# <a name="product-recommendation-prediction"></a>Produktanbefalingsprediksjon

Produktanbefalingsmodellen oppretter sett med prediktive produktanbefalinger. Anbefalingene er basert på tidligere kjøpsatferd og kunder med lignende kjøpsmønstre. Du kan opprette nye produktanbefalingsprediksjoner på siden **Intelligens** > **Prediksjoner**. Velg **Mine prediksjoner** for å se andre prediksjoner du har opprettet.

Produktanbefalinger kan være underlagt lokale lover og forskrifter og kundens forventninger, som modellen ikke er bygget for å spesifikt ta hensyn til.  Som bruker av denne prediktive funksjonen **må du gå gjennom anbefalingene før du leverer dem til kundene dine** for å sikre at du overholder gjeldende lover eller forskrifter, og kundenes forventninger til hva du kan anbefale. 

I tillegg gir utdataene for denne modellen anbefalinger basert på produkt-ID-en. Leveringsmekanismen må tilordne de anslåtte produkt-IDene til passende innhold som kundene dine kan gjøre rede for lokalisering, bildeinnhold og annet bedriftsspesifikk innhold eller oppførsel.

## <a name="sample-guide"></a>Eksempelveiledning

Hvis du er interessert i å prøve denne funksjonen, men ikke har data for å fullføre kravene nedenfor, kan du [opprette en eksempelimplementering](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Forutsetninger

- Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.

- Forretningskunnskap for å forstå ulike typer produkter for virksomheten og hvordan kundene samhandler med dem. Vi støtter anbefalte produkter som tidligere er kjøpt av kundene dine, eller anbefalinger for nye produkter.

- Data om transaksjoner, kjøp og deres historikk:
    - Transaksjons-ID-er for å skille innkjøp eller transaksjoner.
    - Kunde-ID-er for å tilordne transaksjoner for kundene.
    - Dato for transaksjonshendelser som definerer datoene da transaksjonen forekom.
    - Produkt-ID-informasjon for transaksjonen.
    - (Valgfritt) En dataenhet for produktkatalog for å bruke et produktfilter.
    - (Valgfritt) Om en transaksjon er en retur eller ikke.
    - Det semantiske dataskjemaet for kjøp eller transaksjoner krever følgende informasjon:
        - **Transaksjons-ID:** En unik identifikator for et innkjøp eller en transaksjon.
        - **Transaksjonsdato:** Datoen for innkjøpet eller transaksjonen.
        - **Verdien av transaksjonen:** Det numeriske verdibeløpet for kjøpet eller transaksjonen.
        - **Unik produkt-ID:** ID-en til produktet eller tjenesten som er kjøpt, hvis dataene er på et linjevarenivå.
        - (Valgfritt) **Innkjøp eller retur:** Et boolsk felt der verdien *sann* identifiserer at en transaksjon var en retur. Hvis kjøps- eller returdataene ikke leveres, er modellen og **verdien av transaksjonen** negativ. Vi vil også bruke denne informasjonen til å utlede en retur.
- Kjennetegn for foreslåtte data:
    - Tilstrekkelige historiske data: Minst ett år med transaksjonsdata, helst to til tre år for å inkludere noe sesongavhengighet.
    - Flere kjøp per kunde: Tre eller flere transaksjoner per kunde-ID
    - Antall kunder: Minst 100 kunder, helst mer enn 10 000 kunder. Modellen vil mislykkes med færre enn 100 kunder.

> [!NOTE]
> - Modellen krever kundenes transaksjonshistorikk. Definisjonen av en transaksjon er ganske fleksibel. Alle data som beskriver en brukerproduktinteraksjon, kan fungere som inndata. For eksempel å kjøpe et produkt, ta et kurs eller delta på et arrangement.
> - Bare én transaksjonsloggenhet kan konfigureres for øyeblikket. Hvis det finnes flere kjøpsenheter, kan du forene dem i Power Query før datainntak begynner.
> - Hvis ordre- og ordredetaljer er forskjellige enheter, slår du dem sammen før du bruker dem i modellen. Modellen fungerer ikke bare med en ordre-ID eller kvitterings-ID i en enhet.


## <a name="create-a-product-recommendation-prediction"></a>Opprett en produktanbefalingsprediksjon

1. Gå til **Intelligens** > **Prognoser** i Customer Insights.

1. Velg flisen **Modell for produktanbefalinger** og velg **Bruk denne modellen**.
   > [!div class="mx-imgBorder"]
   > ![Flisen Produktanbefalingsmodell med Bruk denne modellen-knappen.](media/product-recommendation-usethismodel.PNG "Flisen Produktanbefalingsmodell med Bruk denne modellen-knappen")

1. Se gjennom informasjonen om modellkravene. Hvis du har de nødvendige dataene, velger du **Start**.

### <a name="name-model"></a>Gi navn til modell

1. Angi et navn på modellen for å skille den fra andre modeller.

1. Angi et navn for utdataenheten bare ved hjelp av bokstaver og tall, uten mellomrom. Det er navnet som modellenheten vil bruke. Velg deretter **Neste**.

### <a name="define-product-recommendation-configuration"></a>Definer produktanbefalingskonfigurasjon

1. Angi **antall produkter** du vil anbefale til en kunde. Denne verdien avhenger av hvordan leveringsmåten fyller ut data. Hvis du kan anbefale tre produkter, angir du denne verdien i henhold til dette.
   
   >[!TIP]
   > Du kan velge **Lagre utkast** når som helst for å lagre prediksjonen som utkast. Du finner utkastprediksjonen på fanen **Mine prediksjoner**.

1. Velg om du vil ta med produkter som kunder nylig har kjøpt, i feltet **Forventet å gjenta innkjøp**.

1. Angi **Se tilbake-vindu**. Denne innstillingen angir tidsrammen modellen vurderer før du anbefaler produktet på nytt til brukeren. Angi for eksempel at en kunde kjøper en bærbar datamaskin annethvert år. Dette vinduet vil se på kjøpshistorikken for de siste to årene, og hvis de finner en vare, filtreres varen fra anbefalingene.

1. Velg **Neste**

### <a name="add-required-data"></a>Legg til obligatoriske data

1. Velg **Legg til data**, og velg aktivitetstypen i sideruten som inneholder den nødvendige informasjonen om transaksjonen eller innkjøpsloggen.

1. Under **Velg aktivitetene** velger du de bestemte aktivitetene fra den valgte aktiviteten du vil at beregningen skal fokusere på.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Sideruten som viser hvordan du velger bestemte aktiviteter under semantisk type.":::

1. Hvis du ikke har tilordnet aktiviteten til en semantisk type ennå, velger du **Rediger** for å gjøre dette. Den veiledede opplevelsen for kartlegging av semantiske aktiviteter åpnes. Tilordne dataene til de tilsvarende feltene i den valgte aktivitetstypen.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Sideinnstilling for aktivitetstype.":::

1. Når du har kartlagt aktiviteten til den tilsvarende semantiske typen, velger du **Neste** for å fortsette 
 
1. Tilordne semantiske attributter til feltene som kreves for å kjøre modellen.

1. Velg **Lagre**.

1. Velg **Neste**.


### <a name="configure-product-filters"></a>Konfigurere produktfiltre

Noen ganger er bare visse produkter gunstige eller passende for den typen prediksjon du bygger. Produktfiltre lar deg identifisere et delsett av produkter med spesifikke egenskaper som anbefales til kundene dine. Modellen vil bruke alle produktene som er tilgjengelige for å lære mønstre, men bare bruke produktene som samsvarer med produktfilteret i utdataene.

1. I trinnet **Legg til produktinformasjon** legger du til produktkatalogen med informasjon for hvert produkt. Tilordne informasjonen som kreves, og velg **Neste**.

3. I trinnet **Produktfiltre** velger du mellom følgende alternativer.

   * **Ingen filtre**: Bruk alle produkte i produktanbefalingsprediksjonen.

   * **Definer spesifikke produktfiltre**: Bruk bestemte produkter i produktanbefalingsprediksjonen.

1. Velg **Neste**.

1. Hvis du velger å definere et produktfilter, må du definere det nå. I **Produktkatalogattributter**-ruten velger du attributtene fra *Produktkatalog-enheten* du vil inkludere i filteret.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Siderute som viser attributtet i produktkatalogenheten som skal velges for produktfiltre.":::

1. Velg om du vil at produktfilteret skal bruke **and**- eller **or**-koblinger til logisk å kombinere ditt utvalg av attributter fra produktkatalogen.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Eksempel på konfigurasjon av produktfiltre kombinert med logiske AND-koblinger.":::

1. Velg **Neste**.

### <a name="set-update-schedule-and-review-configuration"></a>Angi konfigurasjon for oppdateringsplan og gjennomgang

1. Angi en hyppighet for gjenopplæring av modellen. Denne innstillingen er viktig for å oppdatere nøyaktigheten til prognoser når nye data importeres til Customer Insights. De fleste virksomheter kan gjenopplære én gang i måneden og få god nøyaktighet for prognosen.

1. Velg **Neste**.

1. Se gjennom konfigurasjonen. Du kan gå tilbake til en hvilken som helst del av forutsigelseskonfigurasjonen ved å velge **Rediger** under verdien som vises. Du kan også velge et konfigurasjonstrinn fra fremdriftsindikatoren.

1. Hvis alle verdier er konfigurert på riktig måte, velger du **Lagre og kjør** for å starte forutsigelsesprosessen. I kategorien **Mine prediksjoner** kan du vise statusen for prediksjonene. Det kan ta flere timer før prosessen er fullført, avhengig av mengden data som brukes i forutsigelsen.

## <a name="review-a-prediction-status-and-results"></a>Se gjennom en forutsigelsesstatus og resultater

1. Gå til kategorien **Mine prediksjoner** i **Intelligens** > **Prediksjoner**.
   > [!div class="mx-imgBorder"]
   > ![Visning av Mine prediksjoner-siden.](media/product-recommendation-mypredictions.PNG "Visning av Mine prediksjoner-siden")

1. Velg prognosen du vil gå gjennom.
   - **Navn på prediksjon:** Navnet på prediksjonen som ble angitt under opprettingen.
   - **Prediksjonstype:** Typen modell som brukes for prediksjonen.
   - **Utdataenhet:** Navn på enheten for å lagre utdataene fra prediksjonen. Du kan finne en enhet med dette navnet på **Data** > **Enhteter**.    
      *Poengsum* i utdataenheten er et kvantitativt mål på anbefalingen. Modellen anbefaler produkter med høyere poengsum over produkter med lavere poengsum.
   - **Forventet felt:** Dette feltet fylles bare ut for enkelte typer prediksjoner, og brukes ikke i prediksjon av produktanbefaling.
   - **Status:** Gjeldende status for prediksjonskjøringen.
        - **I kø:** Forutsigelsen venter på at andre prosesser kjøres.
        - **Oppdaterer:** Forutsigelsen kjører for øyeblikket "poengsum"-trinnet i behandlingen for å gi resultatene som flyter til utdataenheten.
        - **Mislyktes:** Forutsigelsen mislyktes. Velg **Logger** hvis du vil ha mer informasjon.
        - **Vellykket:** Forutsigelsen var vellykket. Velg **Vis** under de loddrette ellipsene for å gå gjennom forutsigelsen
   - **Redigert:** Datoen da konfigurasjonen av forutsigelsen ble endret.
   - **Sist oppdatert:** Datoen da forutsigelsen oppdaterte resultater i utdataenheten.

1. Velg de loddrette ellipsene ved siden av den forutsigelsen du vil se gjennom resultatene for, og velg **Vis**.
   > [!div class="mx-imgBorder"]
   > ![Visning av alternativer på loddrette ellipser-menyen for en forutsigelse, blant annet rediger, oppdater, vis, logger og slett.](media/product-recommendation-verticalellipses.PNG "Visning av alternativer på loddrette ellipser-menyen for en forutsigelse, blant annet rediger, oppdater, vis, logger og slett")

1. Det finnes fem hoveddeler med data på resultatsiden:
    1. **Ytelse for opplæringsmodell:** A, B eller C er mulige resultater. Denne poengsummen angir ytelsen til forutsigelsen, og kan hjelpe deg med å ta beslutningen om å bruke resultatene som er lagret i utdataenheten.
        - Poengsummer blir fastslått basert på følgende regler:
            - **A** Modellen blir betraktet som **A**-kvalitet hvis måleverdien Suksess ved K er minst 10 % mer enn basisen. 
            - **B** Modellen blir betraktet som **B**-kvalitet hvis måleverdien Suksess ved K er minst 0 % til 10 % mer enn basisen.
            - **C** Modellen blir betraktet som **C**-kvalitet hvis måleverdien Suksess ved K er mindre enn basisen.
               
               > [!div class="mx-imgBorder"]
               > ![Visning av modellytelsesresultatet.](media/product-recommendation-modelperformance.PNG "Visning av modellytelsesresultatet")
            - **Basis**: Modellen tar de mest anbefalte produktene etter kjøpsantall for alle kunder, og bruker lærte regler som identifiseres av modellen, til å opprette et sett med anbefalinger for kundene. Prediksjonene sammenlignes deretter med de mest populære produktene basert på antall kunder som hadde kjøpt produktet. Hvis en kunde har minst ett produkt i de anbefalte produktene som også ble sett blant de mest kjøpte produktene, regnes disse som en del av basisen. Hvis det var ti av disse kundene som hadde et anbefalt produkt kjøpt av 100 kunder totalt, ville den opprinnelige basisen vært 10 %.
            - **Suksess ved K**: Ved hjelp av et valideringssett med tidsperioder for transaksjoner opprettes anbefalinger for alle kunder og sammenlignes med valideringssettet for transaksjoner. I en periode på 12 måneder kan for eksempel 12 måneder settes til side som et valideringssett med data. Hvis modellen forutsier minst én ting du ville kjøpt i måned 12, basert på hva den har lært av de forrige 11 månedene, vil kunden øke måleverdien Suksess ved K.
    
    1. **De fleste foreslåtte produkter (med opptelling):** De fem beste produktene som ble forutsatt for kundene dine.
       > [!div class="mx-imgBorder"]
       > ![Diagram som viser de fem mest anbefalte produktene.](media/product-recommendation-topproducts.PNG "Diagram som viser de fem mest anbefalte produktene")
    
    1. **Viktige anbefalingsfaktorer:** Modellen bruker kundenes transaksjonshistorikk til å gi produktanbefalinger. Den lærer mønstre basert på tidligere kjøp og finner likheter mellom kunder og produkter. Disse likhetene brukes deretter til å generere produktanbefalinger.
    Følgende er faktorene som kan påvirke en produktanbefaling som genereres av modellen. 
        - **Tidligere transaksjoner**: Tidligere kjøpsmønstre ble brukt av modellen til å generere produktanbefalinger. Modellen kan for eksempel anbefale en _Surface Arc-mus_ hvis noen nylig har kjøpt en _Surface Book 3_ og en _Surface-penn_. Modellen lærte at mange kunder historisk sett hadde kjøpt en _Surface Arc-mus_ etter å ha kjøpt en _Surface Book 3_ og en _Surface-penn_.
        - **Kundelikhet**: Et anbefalt produkt ble historisk kjøpt av andre kunder som viser lignende kjøpsmønstre. John ble for eksempel anbefalt _Surface Headphones 2_ fordi Jennifer og Brad nylig kjøpte _Surface Headphones 2_. Modellen mener John ligner på Jennifer og Brad fordi de historisk har hatt lignende kjøpsmønstre.
        - **Produktlikhet**: Et anbefalt produkt ligner på andre produkter som kunden tidligere hadde kjøpt. Modellen anser to produkter for å være like hvis de ble kjøpt sammen eller av lignende kunder. Noen får for eksempel en anbefaling for en _USB-lagringsstasjon_ fordi de tidligere har kjøpt en _USB-C til USB-adapter_, og modellen mener at _USB-lagringsstasjon_ ligner på _USB-C til USB-adapter_ basert på historiske kjøpsmønstre.

        Hver produktanbefaling påvirkes av en eller flere av disse faktorene. Prosentandelen av anbefalinger der hver påvirkningsfaktor spilte en rolle, visualiseres i et diagram. I eksemplet nedenfor ble 100 % av anbefalingene påvirket av tidligere transaksjoner, 60 % av kundelikhet og 22 % av produktlikhet. Hold pekeren over stolpene i diagrammet for å se den nøyaktige prosentandelen der påvirkningsfaktorene bidro.

        > [!div class="mx-imgBorder"]
        > ![Viktige anbefalingsfaktorer.](media/product-recommendation-keyrecommendationfactors.png "Viktige anbefalingsfaktorer lært av modellen for å generere produktanbefalinger")
       
     
   1. **Datastatistikk**: Gir en oversikt over antall transaksjoner, kunder og produkter modellen vurderte. Den er basert på inndata som ble brukt til å lære mønstre og generere produktanbefalinger.

      > [!div class="mx-imgBorder"]
      > ![Datastatistikk.](media/product-recommendation-datastatistics.png "Datastatistikk rundt inn-/utdata som brukes av modellen til å lære mønstre")

      Denne delen viser statistikk rundt datapunktene som ble brukt av modellen til å lære mønstre og generere produktanbefalinger. Filtrering, som konfigurert i modellkonfigurasjonen, vil gjelde for utdataene som genereres av modellen. Modellen bruker imidlertid alle tilgjengelige data til å lære mønstre. Hvis du bruker produktfiltrering i modellkonfigurasjonen, vil derfor denne delen vise totalt antall produkter som modellen analyserte for å lære mønstre, noe som kan avvike fra antall produkter som samsvarer med de definerte filtreringskriteriene.

   1. **Produktanbefalinger med høy sikkerhet**: Et eksempel på anbefalinger gitt til kundene som modellen tror det er sannsynlig at kunden vil kjøpe.    
      Hvis en produktkatalog legges til, erstattes produkt-IDene med produktnavn. Produktnavn gir en mer handlingsrettet og intuitiv informasjon om prediksjonene.
       > [!div class="mx-imgBorder"]
       > ![Liste som viser forslag med høy sikkerhet for et utvalgt sett med individuelle kunder.](media/product-recommendation-highconfidence.PNG "Liste som viser forslag med høy sikkerhet for et utvalgt sett med individuelle kunder")

## <a name="manage-predictions"></a>Administrere prediksjoner

Det går an å optimalisere, feilsøke, oppdatere eller slette prognoser. Se gjennom en brukbarhetsrapport for inndata for å finne ut hvordan du gjør en prediksjon raskere og mer pålitelig. Hvis du vil ha mer informasjon, kan du se [Administrere prediksjoner](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
