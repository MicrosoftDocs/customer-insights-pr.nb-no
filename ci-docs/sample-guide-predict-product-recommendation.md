---
title: Eksempelveiledning for prediksjon for produktanbefaling
description: Bruk denne eksempelveiledningen til å prøve ut den medfølgende prediksjonsmodellen for produktanbefaling.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762698"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Eksempelveiledning for prediksjon for produktanbefaling

Vi tar deg gjennom et helhetlig eksempel på prediksjon av produktanbefaling ved å bruke eksempeldataene som vises nedenfor.

## <a name="scenario"></a>Scenario

Contoso er et firma som produserer kaffe og kaffemaskiner av høy kvalitet, som de kan selge via nettstedet Contoso Coffee. Målet er å forstå hvilke produkter de bør anbefale til sine regelmessige kunder. Hvis du vet hva det er mer **sannsynlig at kundene kjøper**, kan du hjelpe dem med å lagre markedsføringen ved å fokusere på bestemte elementer.

## <a name="prerequisites"></a>Forutsetninger

- Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.
- Vi anbefaler at du implementerer følgende trinn [i et nytt miljø](manage-environments.md).

## <a name="task-1---ingest-data"></a>Oppgave 1 – hente inn data

Se særlig gjennom artiklene [om datainntak](data-sources.md) og [import av datakilder ved å bruke Power Query-koblinger](connect-power-query.md). Følgende informasjon forutsetter at du kjenner til datainntakt generelt.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Hente inn kundedata fra eCommerce-plattform

1. Opprett en datakilde med navnet **eCommerce**, velg importalternativet, og velg koblingen **Tekst/CSV**.

1. Skriv inn URL-adressen for eCommerce-kontakter: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/klokkeslett/sone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformer fødselsdato til dato.":::

1. I Navn-feltet i den høyre ruten endrer du navnet på datakilden fra **Query** til **eCommerceContacts**.

1. **Lagre** datakilden.

### <a name="ingest-online-purchase-data"></a>Hente inn online kjøpsdata

1. Legge til et nyttdata sett i samme **eCommerce**-datakilde. Velg koblingen **Tekst/CSV** på nytt.

1. Skriv inn nettadressen for **Online kjøp**-dataene [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **PurchasedOn**: Dato/klokkeslett
   - **TotalPrice**: Valuta

1. I **Navn**-feltet i sideruten endrer du navnet på datakilden fra **Spørring** til **eCommercePurchases**.

1. **Lagre** datakilden.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Hente inn kundedata fra lojalitetsskjema

1. Opprett en datakilde med navnet **LoyaltyScheme**, velg importalternativet, og velg koblingen **Tekst/CSV**.

1. Skriv inn URL-adressen for eCommerce-kontakter [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltall
   - **CreatedOn**: Dato/klokkeslett

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **loyCustomers**.

1. **Lagre** datakilden.

## <a name="task-2---data-unification"></a>Oppgave 2 – Dataforening

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Oppgave 3 – Konfigurer prediksjon av produktanbefaling

Når de enhetlige kundeprofilene er på plass, kan vi nå kjøre produktanbefalingsprediksjon.

1. Gå til **Intelligens** > **Prediksjon** og velg **Produktanbefaling**.

1. Velg **Komme i gang**.

1. Gi modellen navnet **Prediksjon for OOB-produktanbefalingsmodell** og utdataenheten **OOBProductRecommendationModelPrediction**.

1. Definer tre betingelser for modellen:

   - **Antall produkter**: Angi **5** for denne verdien. Denne innstillingen definerer hvor mange produkter du vil anbefale til kundene.

   - **Forventet å gjenta innkjøp**: Velg **Ja** for å angi at du vil ta med produkter som kundene har kjøpt tidligere, i anbefalingen.

   - **Tilbakeblikksvindu:** Velg minst **365 dager**. Denne innstillingen definerer hvor langt modellen skal se bakover for å se på kundens aktivitet og bruke det som inndata i anbefalingene.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modellinnstillinger for produktanbefalingsmodellen.":::

1. Velg **Legg til data** i trinnet **Legg til obligatoriske data**.

1. Velg **SalesOrderLine** som innkjøpsloggenhet i ruten **Legg til data**. Nå er det sannsynligvis ikke konfigurert ennå. Åpne koblingen i ruten for å opprette aktiviteten med følgende trinn:
   1. Skriv inn et **aktivitetsnavn**, og velg *eCommercePurchases:eCommerce* som **aktivitetsenhet**. **Primærnøkkelen** er *PurchaseId*.
   1. Definer og gi relasjonen navnet til *eCommerceContacts:eCommerce-enheten* og velg **ContactId** som sekundærnøkkel.
   1. For aktivitetssamling angir du **Hendelsesaktivitet** som *TotalPrice* og Timestamp til *PurchasedOn*. Du kan angi flere felter som angitt i [kundeaktiviteter](activities.md).
   1. Velg **SalesOrderLine** for *aktivitetstype*. Tildel følgende aktivitetsfelter:
      - Ordrelinje-ID: PurchaseId
      - Ordre-ID: PurchaseId
      - Ordredata: PurchasedOn
      - Produkt-ID: ProductId
      - Beløp: TotalPrice
   1. Se gjennom og fullfør aktiviteten før du går tilbake til modellkonfigurasjonen.

1. Tilbake i **Velg aktiviteter**-trinnet velger du den nylig opprettede aktiviteten i **Aktiviteter**-delen. Velg **Neste** og attributtildelingen er allerede fylt ut. Velg **Lagre**.

1. I denne eksempelhåndboken hopper vi over settet **Legg til produktinformasjon** og **Produktfiltre** fordi vi ikke har produktinformasjonsdata.

1. Angi modelltidsplanen i trinnet **Dataoppdateringer**.

   Modellen må læres opp regelmessig for å lære nye mønstre når nye data er hentet inn. I dette eksemplet velger du **Månedlig**.

1. Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**. Det tar noen minutter å kjøre modellen første gang.

## <a name="task-4---review-model-results-and-explanations"></a>Oppgave 4 – gå gjennom modellresultater og forklaringer

La modellen fullføre opplæringen og beregne poengsum for dataene. Du kan nå se gjennom forklaringer av modellen for produktanbefaling. Hvis du vil ha mer informasjon, kan du se [Gå gjennom en prediksjonsstatus og resultater](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Oppgave 5 – Opprett et segment av mye kjøpte produkter

Når du kjører produksjonsmodellen, opprettes det en ny enhet som du kan se i **Data** > **Enheter**.

Du kan opprette et nytt segment basert på enheten som er opprettet av modellen.

1. Gå til **Segmenter**. Velg **Ny** og velg **Opprett fra intelligens**.

   ![Opprette et segment med modellutdataene.](media/segment-intelligence.png)

1. Velg **OOBProductRecommendationModelPrediction**-endepunktet, og definer segmentet:

   - Felt: ProductID
   - Verdi: Velg de tre mest populære produkt-ID-ene

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Opprett et segment fra modellresultatene.":::

Du har nå et segment som oppdateres dynamisk, og denne identifiserer kundene som kan være interessert i å kjøpe de tre mest anbefalte produktene.

Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
