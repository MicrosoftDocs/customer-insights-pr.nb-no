---
title: Forutsi produktanbefalinger
description: Forutsi produktene en kunde sannsynligvis kommer til å kjøpe eller samhandle med.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610294"
---
# <a name="predict-product-recommendations"></a>Forutsi produktanbefalinger

Produktanbefalingsmodellen oppretter sett med prediktive produktanbefalinger. Anbefalingene er basert på tidligere kjøpsatferd og kunder med lignende kjøpsmønstre. Denne modellen er for enkeltforbrukere (B2C).

Du må ha forretningskunnskap om ulike typer produkter for virksomheten og hvordan kundene samhandler med dem. Vi støtter anbefalte produkter som tidligere er kjøpt av kundene dine, eller anbefalinger for nye produkter.

Produktanbefalinger kan være underlagt lokale lover og forskrifter og kundens forventninger, som modellen ikke er bygget for å spesifikt ta hensyn til. Derfor **må du gå gjennom anbefalingene før du leverer dem til kundene dine** for å sikre at du følger gjeldende lover eller forskrifter og oppfyller kundenes forventninger til hva du kan anbefale.

Utdataene fra denne modellen gir anbefalinger basert på produkt-ID-en. Leveringsmekanismen må tilordne de forutsagte produkt-ID-ene til passende innhold for kundene dine for å gjøre rede for lokalisering, bildeinnhold og annet bedriftsspesifikk innhold eller funksjonalitet.

> [!TIP]
> Prøv produktanbefalingsprediksjonen ved hjelp av eksempeldata: [Eksempelveiledning for produktanbefalingsprediksjon](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Forutsetning

- Minst [Bidragsyter-tillatelser](permissions.md)
- Minst 100 kunder, helst flere enn 10 000 kunder.
- Kundeidentifikator, en unik identifikator for å samsvare transaksjoner med en individuell kunde
- Minst ett år med transaksjonsdata, helst to til tre år for å inkludere noe sesongavhengighet. Ideelt sett minst tre eller flere transaksjoner per kunde-ID. Transaksjonsloggen må inneholde følgende:
  - **Transaksjons-ID**: Unik identifikator for et innkjøp eller en transaksjon.
  - **Transaksjonsdato**: Dato for innkjøpet eller transaksjonen.
  - **Verdien av transaksjonen**: Numerisk verdi for kjøpet eller transaksjonen.
  - **Unik produkt-ID**: ID-en til produktet eller tjenesten som er kjøpt, hvis dataene er på et linjevarenivå.
  - **Kjøp eller retur**: En boolsk verdi (true/false) der verdien *true* identifiserer at en transaksjon var en retur. Hvis kjøps- eller returdataene ikke er i modellen og **verdien av transaksjonen** er negativ, konkluderer vi at det er snakk om en retur.
- En dataenhet for produktkatalog som brukes som et produktfilter.

> [!NOTE]
> - Modellen krever transaksjonsloggen for kundene der transaksjonen er alle data som beskriver en interaksjon mellom bruker og produkt. For eksempel å kjøpe et produkt, ta et kurs eller delta på et arrangement.
> - Bare én transaksjonsloggenhet kan konfigureres. Hvis det finnes flere kjøpsenheter, kan du kombinere dem i Power Query før datainntak begynner.
> - Hvis ordre- og ordredetaljer er forskjellige enheter, slår du dem sammen før du bruker dem i modellen. Modellen fungerer ikke bare med en ordre-ID eller kvitterings-ID i en enhet.

## <a name="create-a-product-recommendation-prediction"></a>Opprett en produktanbefalingsprediksjon

Velg **Lagre utkast** når som helst for å lagre prediksjonen som utkast. Ukastprediksjonen vises i fanen **Mine prediksjoner**.

1. Gå til **Intelligens** > **Prediksjoner**.

1. Velg **Bruk modell** på flisen **Produktanbefalinger (forhåndsversjon)** i **Opprett**-fanen.

1. Velg **Komme i gang**.

1. **Gi navn til denne modellen** og **Navn på utdataenheten** for å skille dem fra andre modeller eller enheter.

1. Velg **Neste**.

### <a name="define-product-recommendation-preferences"></a>Definer preferanser for produktanbefaling

1. Angi **Antall produkter** du vil anbefale for en kunde. Denne verdien avhenger av hvordan leveringsmåten fyller ut data.

1. Velg om du vil ta med produkter som kunder tidligere har kjøpt, i feltet **Forventet å gjenta innkjøp**.

1. Angi **Se tilbake-vindu** med tidsrammen modellen vurderer før du anbefaler produktet på nytt til brukeren. Angi for eksempel at en kunde kjøper en bærbar datamaskin annethvert år. Modellen ser på kjøpshistorikken for de siste to årene, og hvis den finner en vare, filtreres varen fra anbefalingene.

1. Velg **Neste**

### <a name="add-purchase-history"></a>Legg til kjøpshistorikk

1. Velg **Legg til data** for **Historikk for kundetransaksjon**.

1. Velg den semantiske aktivitetstypen **SalesOrderLine** som inneholder den nødvendige informasjonen i transaksjonsloggen eller kjøpshistorikken. Hvis aktiviteten ikke er konfigurert, velger du **her** og oppretter den.

1. Hvis aktivitetsattributtene ble tilordnet semantisk da aktiviteten ble opprettet, velger du de bestemte attributtene eller enheten du vil at beregningen skal fokusere på, under **Aktiviteter**. Hvis semantisk tilordning ikke forekom, velger du **Rediger** og tilordner dataene.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Sideruten som viser hvordan du velger bestemte aktiviteter under semantisk type.":::

1. Velg **Neste**, og se gjennom attributtene som kreves for denne modellen.

1. Velg **Lagre**.

1. Velg **Neste**.

### <a name="add-product-information-and-filters"></a>Legg til produktinformasjon og -filtre

Noen ganger er bare visse produkter gunstige eller passende for den typen prediksjon du bygger. Bruk produktfiltre til å identifisere et delsett av produkter med bestemte kjennetegn som anbefales til kundene dine. Modellen vil bruke alle produktene som er tilgjengelige for å lære mønstre, men bare bruke produktene som samsvarer med produktfilteret i utdataene.

1. Legg til produktkatalogenheten som inneholder informasjon for hvert produkt. Tilordne informasjonen som kreves, og velg **Lagre**.

1. Velg **Neste**.

1. Velg **Produktfiltre**:

   - **Ingen filtre**: Bruk alle produkte i produktanbefalingsprediksjonen.

   - **Definer spesifikke produktfiltre**: Bruk bestemte produkter i produktanbefalingsprediksjonen. I ruten **Produktkatalogattributter** velger du attributtene fra produktkatalogenheten du vil ta med i filteret.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Siderute som viser attributtet i produktkatalogenheten som skal velges for produktfiltre.":::

1. Velg om du vil at produktfilteret skal bruke **and** eller **or** til logisk å kombinere ditt utvalg av attributter fra produktkatalogen.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Eksempel på konfigurasjon av produktfiltre kombinert med logiske AND-koblinger.":::

1. Velg **Neste**.

### <a name="set-update-schedule"></a>Angi oppdateringstidsplan

1. Velg en hyppighet for å lære opp modellen på nytt. Denne innstillingen er viktig for å oppdatere nøyaktigheten til prediksjoner etter hvert som nye data tas inn i Customer Insights. De fleste virksomheter kan gjenopplære én gang i måneden og få god nøyaktighet for prognosen.

1. Velg **Neste**.

### <a name="review-and-run-the-model-configuration"></a>Se gjennom og kjøre modellkonfigurasjonen

Trinnet **Se gjennom og kjør** viser et sammendrag av konfigurasjonen og lar deg gjøre endringer før du oppretter prediksjonen.

1. Velg **Rediger** i et av trinnene for å se gjennom og gjøre endringer.

1. Hvis du er fornøyd med valgene, velger du **Lagre og kjør** for å begynne å kjøre modellen. Velg **Ferdig**. Fanen **Mine prediksjoner** vises mens prediksjon opprettes. Det kan ta flere timer før prosessen er fullført, avhengig av mengden data som brukes i forutsigelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vis prediksjonsresultater

1. Gå til **Intelligens** > **Prediksjoner**.

1. I fanen **Mine prediksjoner** velger du prediksjonen du vil vise.

Det finnes fem hoveddeler med data på resultatsiden.

- **Modellytelse:** Graderingene A, B eller C angir ytelsen til prediksjonen og kan hjelpe deg å ta beslutningen om å bruke resultatene som er lagret i utdataenheten.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Bilde av modellytelsesresultatet med graderingen A.":::

  Vurderinger fastsettes basert på følgende regler:
  - **A** når måleverdien Suksess ved K er minst 10 % mer enn basisen.
  - **B** når måleverdien Suksess ved K er 0 % til 10 % mer enn basisen.
  - **C** når måleverdien Suksess ved K er mindre enn basisen.
  - **Basis**: De mest anbefalte produktene etter kjøpsantall for alle kunder + lærte regler som identifiseres av modellen = et sett med anbefalinger for kundene. Prediksjonene sammenlignes deretter med de mest populære produktene basert på antall kunder som hadde kjøpt produktet. Hvis en kunde har minst ett produkt i de anbefalte produktene som også ble sett blant de mest kjøpte produktene, regnes disse som en del av basisen. Hvis ti av disse kundene for eksempel hadde et anbefalt produkt kjøpt av 100 kunder totalt, er basisen 10 %.
  - **Suksess ved K**: Anbefalinger opprettes for alle kunder og sammenlignes med valideringssettet i tidsperioden med transaksjoner. I en periode på 12 måneder kan for eksempel måned 12 settes til side som et valideringssett med data. Hvis modellen forutsier minst én ting du ville kjøpt i måned 12, basert på hva den har lært av de forrige 11 månedene, vil kunden øke måleverdien Suksess ved K.

- **De fleste foreslåtte produkter (med opptelling):** De fem beste produktene som ble forutsatt for kundene dine.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Diagram som viser de fem mest anbefalte produktene.":::

- **Viktige anbefalingsfaktorer:** Modellen bruker kundenes transaksjonshistorikk til å gi produktanbefalinger. Den lærer mønstre basert på tidligere kjøp og finner likheter mellom kunder og produkter. Disse likhetene brukes deretter til å generere produktanbefalinger.
  Følgende faktorer kan påvirke en produktanbefaling som genereres av modellen.
  - **Tidligere transaksjoner**: Et anbefalt produkt var basert på tidligere kjøpsmønstre. Modellen kan for eksempel anbefale en *Surface Arc-mus* hvis noen nylig har kjøpt en *Surface Book 3* og en *Surface-penn*. Modellen lærte at mange kunder historisk sett hadde kjøpt en *Surface Arc-mus* etter å ha kjøpt en *Surface Book 3* og en *Surface-penn*.
  - **Kundelikhet**: Et anbefalt produkt ble historisk kjøpt av andre kunder som viser lignende kjøpsmønstre. John ble for eksempel anbefalt *Surface Headphones 2* fordi Jennifer og Brad nylig kjøpte *Surface Headphones 2*. Modellen mener John ligner på Jennifer og Brad fordi de historisk har hatt lignende kjøpsmønstre.
  - **Produktlikhet**: Et anbefalt produkt ligner på andre produkter som kunden tidligere hadde kjøpt. Modellen anser to produkter for å være like hvis de ble kjøpt sammen eller av lignende kunder. Noen får for eksempel en anbefaling for en *USB-lagringsstasjon* fordi de tidligere har kjøpt en *USB-C til USB-adapter*, og modellen mener at *USB-lagringsstasjon* ligner på *USB-C til USB-adapter* basert på historiske kjøpsmønstre.

  Hver produktanbefaling påvirkes av en eller flere av disse faktorene. Prosentandelen av anbefalinger der hver påvirkningsfaktor spilte en rolle, visualiseres i et diagram. I eksemplet nedenfor ble 100 % av anbefalingene påvirket av tidligere transaksjoner, 60 % av kundelikhet og 22 % av produktlikhet. Hold pekeren over stolpene i diagrammet for å se den nøyaktige prosentandelen der påvirkningsfaktorene bidro.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Viktige anbefalingsfaktorer lært av modellen for å generere produktanbefalinger.":::

- **Datastatistikk**: En oversikt over antall transaksjoner, kunder og produkter modellen vurderte. Den er basert på inndata som ble brukt til å lære mønstre og generere produktanbefalinger.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Datastatistikk rundt inn-/utdata som brukes av modellen til å lære mønstre.":::
  
  Modellen bruker alle tilgjengelige data til å lære mønstre. Hvis du bruker produktfiltrering i modellkonfigurasjonen, viser denne delen totalt antall produkter som modellen analyserte for å lære mønstre, noe som kan avvike fra antall produkter som samsvarer med de definerte filtreringskriteriene. Filtrering brukes på utdataene som genereres av modellen.

- **Eksempel på produktanbefalinger**: Et eksempel på anbefalinger som modellen tror det er sannsynlig at kunden vil kjøpe. Hvis en produktkatalog legges til, erstattes produkt-ID-ene med produktnavn.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Liste som viser forslag med høy sikkerhet for et utvalgt sett med individuelle kunder.":::

> [!NOTE]
> I utdataenheten for denne modellen viser *Poengsum* det kvantitative målet for anbefalingen. Modellen anbefaler produkter med høyere poengsum over produkter med lavere poengsum. Hvis du vil vise poengsummen, går du til **Data** > **Enheter** og viser datafanen for utdataenheten du definerte for denne modellen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
