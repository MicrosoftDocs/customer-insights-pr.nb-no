---
title: Eksempelveiledning for prediksjon av produktanbefaling
description: Bruk denne eksempelveiledningen til å prøve ut den medfølgende prediksjonsmodellen for produktanbefaling.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610156"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Eksempelveiledning for prediksjon av produktanbefaling

Denne veiledningen går gjennom et helhetlig eksempel på prediksjon av produktanbefaling ved hjelp av eksempeldata. Vi anbefaler at du prøver denne prediksjonen [i et nytt miljø](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso er et selskap som produserer kaffe og kaffemaskiner av høy kvalitet. De selger produktene via nettstedet til Contoso Coffee. Målet er å forstå hvilke produkter de bør anbefale til sine regelmessige kunder. Hvis du vet hva det er mer **sannsynlig at kundene kjøper**, kan du hjelpe dem å lagre markedsføringen ved å fokusere på bestemte elementer.

## <a name="prerequisites"></a>Forutsetning

- Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.

## <a name="task-1---ingest-data"></a>Oppgave 1 – hente inn data

Se gjennom artiklene [om datainntak](data-sources.md) og [koble til en Power Query-datakilde](connect-power-query.md). Følgende informasjon forutsetter at du er fortrolig med datainntak generelt.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Hente inn kundedata fra eCommerce-plattform

1. Opprett en Power Query-datakilde kalt **eCommerce**, og velg **Tekst/CSV**-koblingen.

1. Skriv inn nettadressen for eCommerce-kontakter: https://aka.ms/ciadclasscontacts.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/klokkeslett/sone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformer fødselsdato til dato.":::

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden til **eCommerceContacts**.

1. **Lagre** datakilden.

### <a name="ingest-online-purchase-data"></a>Hente inn online kjøpsdata

1. Legge til et nyttdata sett i samme **eCommerce**-datakilde. Velg koblingen **Tekst/CSV** på nytt.

1. Skriv inn nettadressen til dataene for online kjøp: https://aka.ms/ciadclassonline.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **PurchasedOn**: Dato/klokkeslett
   - **TotalPrice**: Valuta

1. I **Navn**-feltet i sideruten endrer du navnet på datakilden til **eCommercePurchases**.

1. **Lagre** datakilden.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Hente inn kundedata fra lojalitetsskjema

1. Opprett en datakilde kalt **LoyaltyScheme**, og velg koblingen **Tekst/CSV**.

1. Angi nettadressen til lojale kunder: https://aka.ms/ciadclasscustomerloyalty.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltall
   - **CreatedOn**: Dato/klokkeslett

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden til **loyCustomers**.

1. **Lagre** datakilden.

## <a name="task-2---data-unification"></a>Oppgave 2 – Dataforening

Gå gjennom artikkelen [om datasamling](data-unification.md). Følgende informasjon forutsetter at du er fortrolig med datasamling generelt.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Oppgave 3 – opprett aktivitet for transaksjonslogg

Se gjennom artikkelen [om kundeaktiviteter](activities.md). Følgende informasjon forutsetter at du er fortrolig med opprettelse av aktiviteter generelt.

1. Opprett en aktivitet kalt **eCommercePurchasesmed** med enheten *eCommercePurchases:eCommerce* og primærnøkkelen for den, **PurchaseId**.

1. Opprett en relasjon mellom *eCommercePurchases:eCommerce* og *eCommerceContacts:eCommerce* med **ContactID** som sekundærnøkkelen for å koble sammen de to enhetene.

1. Velg **TotalPrice** for **EventActivity** og **PurchasedOn** for **TimeStamp**.

1. Velg **SalesOrderLine** for **Aktivitetstype**, og tilordne aktivitetsdataene semantisk.

1. Kjør aktiviteten.

## <a name="task-4---configure-product-recommendation-prediction"></a>Oppgave 4 – Konfigurer prediksjon av produktanbefaling

Når de enhetlige kundeprofilene er på plass og aktivitet opprettet, kjører du produktanbefalingsprediksjon.

1. Gå til **Intelligens** > **Prediksjoner**.

1. Velg **Bruk modell** på flisen **Produktanbefalinger (forhåndsversjon)** i **Opprett**-fanen.

1. Velg **Komme i gang**.

1. Gi modellen navnet **Prediksjon av OOB-produktanbefalingsmodell** og utdataenheten **OOBProductRecommendationModelPrediction**.

1. Velg **Neste**.

1. Definer modellinnstillinger:
   - **Antall produkter**: **5** for å definere hvor mange produkter du vil anbefale til kundene.
   - **Forventet å gjenta innkjøp**: **Ja** for å ta med produkter som tidligere er kjøpt, i anbefalingen.
   - **Se tilbake-vindu:** **365 dager** for å definere hvor langt modellen skal se tilbake før du anbefaler et produkt på nytt.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modellinnstillinger for produktanbefalingsmodellen.":::

1. Velg **Neste**.

1. Velg **Legg til data** i trinnet **Legg til kjøpshistorikk**.

1. Velg **SalesOrderLine** og enheten eCommercePurchases, og velg **Neste**. De obligatoriske dataene blir automatisk fylt ut fra aktiviteten. Velg **Lagre** og deretter **Neste**.

1. Hopp over trinnene **Legg til produktinformasjon** og **Produktfiltre** siden vi ikke har produktinformasjonsdata.

1. Velg **Månedlig** for modelltidsplanen i **Dataoppdateringer**.

1. Velg **Neste**.

1. Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**.

## <a name="task-5---review-model-results-and-explanations"></a>Oppgave 5 – gå gjennom modellresultater og forklaringer

La modellen fullføre opplæringen og beregne poengsum for dataene. Se gjennom [forklaringer av modellen for produktanbefaling](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Oppgave 6 – Opprett et segment av mye kjøpte produkter

Når du kjører modellen, opprettes en ny entitet som vises i **Data** > **Enheter**. Du kan opprette et nytt segment basert på enheten som er opprettet av modellen.

1. Velg **Opprett segment** på resultatsiden.

1. Opprett en regel ved å bruke enheten **OOBProductRecommendationModelPrediction**, og definer segmentet:
   - **Felt**: ProductID
   - **Verdi**: Velg de tre mest populære produkt-ID-ene

1. Velg **Lagre**, og **Kjør** segmentet.

Du har nå et segment som oppdateres dynamisk, og denne identifiserer kundene som kan være interessert i å kjøpe de fem mest anbefalte produktene. Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).

> [!TIP]
> Du kan også opprette et segment for en prediksjonsmodell på **Segmenter**-siden ved å velge **Ny** og velge **Opprett fra** > **Intelligens**. Hvis du vil ha mer informasjon, kan du se [Opprett et nytt segment med hurtigsegmenter](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
