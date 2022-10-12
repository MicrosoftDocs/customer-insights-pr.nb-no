---
title: Eksempelveiledning for prognose på transaksjonelt frafall
description: Bruk denne eksempelveiledningen til å prøve ut den medfølgende prediksjonsmodellen for transaksjonelt frafall.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609696"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Eksempelveiledning for prognose på transaksjonelt frafall

Denne veiledningen går gjennom et helhetlig eksempel på prediksjon av transaksjonsfrafall ved hjelp av eksempeldata. Vi anbefaler at du prøver denne prediksjonen [i et nytt miljø](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso er et selskap som produserer kaffe og kaffemaskiner av høy kvalitet. De selger produktene via nettstedet til Contoso Coffee. Målet er å vite hvilke kunder som vanligvis kjøper produktene deres regelmessig, og som vil slutte å være aktive kunder i løpet av de neste 60 dagene. Det å vite hvilke av kundene som har **sannsynlighet for frafall**, kan hjelpe dem med å spare markedsføringsinnsats ved å fokusere på å beholde dem.

## <a name="prerequisites"></a>Forutsetning

- Minst [bidragsytertillatelser](permissions.md).

## <a name="task-1---ingest-data"></a>Oppgave 1 – hente inn data

Se gjennom artiklene [om datainntak](data-sources.md) og [koble til en Power Query-datakilde](connect-power-query.md). Følgende informasjon forutsetter at du er fortrolig med datainntak generelt.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Hente inn kundedata fra eCommerce-plattform

1. Opprett en datakilde kalt **eCommerce**, og velg koblingen **Tekst/CSV**.

1. Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscontacts.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:

   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/klokkeslett/sone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformer fødselsdato til dato.":::

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden til **eCommerceContacts**

1. Lagre datakilden.

### <a name="ingest-online-purchase-data"></a>Hente inn online kjøpsdata

1. Legge til et nyttdata sett i samme **eCommerce**-datakilde. Velg koblingen **Tekst/CSV** på nytt.

1. Skriv inn nettadressen til dataene for online kjøp: https://aka.ms/ciadclassonline.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:

   - **PurchasedOn**: Dato/klokkeslett
   - **TotalPrice**: Valuta

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden til **eCommercePurchases**.

1. Lagre datakilden.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Hente inn kundedata fra lojalitetsskjema

1. Opprett en datakilde kalt **LoyaltyScheme**, og velg koblingen **Tekst/CSV**.

1. Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscustomerloyalty.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:

   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltall
   - **CreatedOn**: Dato/klokkeslett

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden til **loyCustomers**.

1. Lagre datakilden.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Oppgave 4 – Konfigurere prognosen for transaksjonelt frafall

Når de enhetlige kundeprofilene er på plass og aktivitet opprettet, kjører du transaksjonsfrafallprediksjonen.

1. Gå til **Intelligens** > **Prediksjoner**.

1. Velg **Bruk modell** på **Modell for kundefrafall** i **Opprett**-fanen.

1. Velg **Transaksjonell** for frafallstypen og deretter **Kom i gang**.

1. Gi modellen navnet **Frafallsprognose for OOB eCommerce-transaksjon**, og gi utdataenheten navnet **OOBeCommerceChurnPrediction**.

1. Velg **Neste**.

1. Definer modellinnstillinger:

   - **Prediksjonsvindu**: **60** dager for å definere hvor langt inn i fremtiden vi ønsker å forutsi kundefrafall.

   - **Frafallsdefinisjon**: **60** dager for å angi varigheten uten å kjøpe noe etter at en kunde anses som frafalt.

     :::image type="content" source="media/model-levers.PNG" alt-text="Velg modellinnstillingene Prediksjonsvindu og Frafallsdefinisjon.":::

1. Velg **Neste**.

1. Velg **Kjøpshistorikk (obligatorisk)**, og velg **Legg til data** for kjøpshistorikken.

1. Velg **SalesOrderLine** og enheten eCommercePurchases, og velg **Neste**. De obligatoriske dataene blir automatisk fylt ut fra aktiviteten. Velg **Lagre** og deretter **Neste**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Slå sammen eCommerce-enheter.":::

1. Hopp over trinnet **Tilleggsdata (valgfritt)**.

1. Velg **Månedlig** for modelltidsplanen i **Dataoppdateringer**.

1. Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**.

## <a name="task-5---review-model-results-and-explanations"></a>Oppgave 5 – gå gjennom modellresultater og forklaringer

La modellen fullføre opplæringen og beregne poengsum for dataene. Se gjennom forklaringene på frafallsmodellen. Hvis du vil ha mer informasjon, kan du se [Vis prediksjonsresultater](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Oppgave 6 – Opprette et segment med kunder med høy risiko for frafall

Når du kjører produksjonsmodellen, opprettes en ny entitet som vises i **Data** > **Enheter**. Du kan opprette et nytt segment basert på enheten som er opprettet av modellen.

1. Velg **Opprett segment** på resultatsiden.

1. Opprett en regel ved å bruke enheten **OOBeCommerceChurnPrediction**, og definer segmentet:
   - **Felt**: ChurnScore
   - **Operator**: større enn
   - **Verdi**: 0,6

1. Velg **Lagre**, og **Kjør** segmentet.

Du har nå et segment som oppdateres dynamisk, og som identifiserer kunder med høy risiko for frafall. Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).

> [!TIP]
> Du kan også opprette et segment for en prediksjonsmodell på **Segmenter**-siden ved å velge **Ny** og velge **Opprett fra** > **Intelligens**. Hvis du vil ha mer informasjon, kan du se [Opprett et nytt segment med hurtigsegmenter](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
