---
title: Eksempelveiledning for prognose på abonnementsfrafall
description: Bruk denne eksempelveiledningen til å prøve ut den medfølgende prediksjonsmodellen for abonnementsfrafall.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610018"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Eksempelveiledning for prognose på abonnementsfrafall

Denne veiledningen går gjennom et helhetlig eksempel på prediksjon av abonnementsfrafall ved hjelp av eksempeldata. Vi anbefaler at du prøver denne prediksjonen [i et nytt miljø](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso er et selskap som produserer kaffe og kaffemaskiner av høy kvalitet. De selger produktene via nettstedet til Contoso Coffee. De har nylig startet et abonnementsselskap for kundene for å få kaffe på en jevn basis. Målet deres er å forstå hvilke kunder med abonnement som kanskje vil annullere abonnementet i løpet av de neste månedene. Det å vite hvilke av kundene som **sannsynligvis kommer til å falle fra**, kan hjelpe dem å spare markedsføringsarbeid ved å fokusere på å beholde dem.

## <a name="prerequisites"></a>Forutsetning

- Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.

## <a name="task-1---ingest-data"></a>Oppgave 1 – hente inn data

Se gjennom artiklene [om datainntak](data-sources.md) og [koble til en Power Query-datakilde](connect-power-query.md). Følgende informasjon forutsetter at du er fortrolig med datainntak generelt.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Hente inn kundedata fra eCommerce-plattform

1. Opprett en Power Query-datakilde kalt **eCommerce**, og velg **Tekst/CSV**-koblingen.

1. Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscontacts.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/klokkeslett/sone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformer fødselsdato til dato.":::

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden til **eCommerceContacts**

1. Lagre datakilden.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Hente inn kundedata fra lojalitetsskjema

1. Opprett en datakilde kalt **LoyaltyScheme**, og velg koblingen **Tekst/CSV**.

1. Angi nettadressen til lojalitetskunder: https://aka.ms/ciadclasscustomerloyalty.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltall
   - **CreatedOn**: Dato/klokkeslett

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden til **loyCustomers**.

1. Lagre datakilden.

### <a name="ingest-subscription-information"></a>Hente inn informasjon abonnement

1. Opprett en datakilde kalt **SubscriptionHistory**, og velg koblingen **Tekst/CSV**.

1. Angi nettadressen for abonnementer: https://aka.ms/ciadchurnsubscriptionhistory.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **SubscriptioID**: Heltall
   - **SubscriptionAmount**: Valuta
   - **SubscriptionEndDate**: Dato/klokkeslett
   - **SubscriptionStartDate**: Dato/klokkeslett
   - **TransactionDate**: Dato/klokkeslett
   - **IsRecurring**: Sann/usann
   - **Is_auto_renew**: Sann/usann
   - **RecurringFrequencyInMonths**: Heltall

1. I **Navn**-feltet i ruten til høyre endrer du navnet på datakilden til **SubscriptionHistory**.

1. Lagre datakilden.

### <a name="ingest-customer-data-from-website-reviews"></a>Hente inn kundedata fra gjennomganger av nettsteder

1. Opprett en datakilde kalt **Website**, og velg koblingen **Tekst/CSV**.

1. Angi nettadressen til anmeldelser av nettsteder: https://aka.ms/ciadclasswebsite.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **ReviewRating**: Whole Heltall
   - **ReviewDate**: Dato

1. I **Navn**-feltet i ruten til høyre endrer du navnet på datakilden til **webReviews**.

## <a name="task-2---data-unification"></a>Oppgave 2 – Dataforening

Gå gjennom artikkelen [om datasamling](data-unification.md). Følgende informasjon forutsetter at du er fortrolig med datasamling generelt.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Oppgave 3 – opprett aktivitet for transaksjonslogg

Se gjennom artikkelen [om kundeaktiviteter](activities.md). Følgende informasjon forutsetter at du er fortrolig med opprettelse av aktiviteter generelt.

1. Opprett en aktivitet kalt **SubscriptionHistory** med enheten *Subscription* og primærnøkkelen for den, **CustomerId**.

1. Opprett en relasjon mellom *SubscriptionHistory:Subscription* og *eCommerceContacts:eCommerce* med **CustomerID** som sekundærnøkkelen for å koble sammen de to enhetene.

1. Velg **SubscriptionType** for **EventActivity** og **SubscriptionEndDate** for **TimeStamp**.

1. Velg **Subscription** for **Aktivitetstype**, og tilordne aktivitetsdataene semantisk.

1. Kjør aktiviteten.

1. Legg til en ny aktivitet, og tilordne feltnavnene til de tilsvarende feltene:
   - Enhet for kundeaktivitet: Reviews:Website
   - Primærnøkkel: Website.Reviews.ReviewId
   - Tidsstempel: Website.Reviews.ReviewDate
   - Hendelse (aktivitetsnavn): Website.Reviews.ActivityTypeDisplay
   - Detaljer (beløp eller verdi): Website.Reviews.ReviewRating

1. Kjør aktiviteten.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Oppgave 4 – Konfigurere prognosen for abonnementsfrafall

Med de enhetlige kundeprofilene på plass og aktivitet opprettet kjører du prediksjonen for abonnementsfrafall. Hvis du vil ha detaljerte trinn, kan du se [Frafallsprediksjon for abonnement](predict-subscription-churn.md).

1. Gå til **Intelligens** > **Prediksjoner**.

1. Velg **Bruk modell** på flisen **Modell for kundefrafall** i **Opprett**-fanen.

1. Velg **Abonnement** for frafallstypen og deretter **Kom i gang**.

1. Gi modellen navnet **Frafallsprognose for OOB-abonnement**, og gi utdataenheten navnet **OOBSubscriptionChurnPrediction**.

1. Definer modellinnstillinger:
   - **Dager siden abonnementet ble avsluttet**: **60** dager på å angi at en kunde betraktes som frafalt hvis kunden ikke fornyer abonnementet i denne perioden etter at abonnementet er avsluttet.
   - **Dager det skal søkes inn i fremtid for å forutsi frafall**: **93** dager, som er varigheten modellen forutsier hvilke kunder som kan komme til å falle fra. Jo lenger inn i fremtiden som du ser, jo mindre nøyaktig blir resultatet.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Velg modellinnstillingene og frafallsdefinisjonen.":::

1. Velg **Neste**.

1. I trinnet **Obligatoriske data** velger du **Legg til data** for å oppgi abonnementshistorikk.

1. Velg **Subscription** og enheten SubscriptionHistory, og velg **Neste**. De obligatoriske dataene blir automatisk fylt ut fra aktiviteten. Velg **Lagre**.

1. Velg **Legg til data** under Kundeaktiviteter.

1. I dette eksemplet legger du til nettanmeldelsesaktiviteten.

1. Velg **Neste**.

1. Velg **Månedlig** for modelltidsplanen i **Dataoppdateringer**.

1. Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**.

## <a name="task-5---review-model-results-and-explanations"></a>Oppgave 5 – gå gjennom modellresultater og forklaringer

La modellen fullføre opplæringen og beregne poengsum for dataene. Se gjennom forklaringene på modellen for abonnementsfrafall. Hvis du vil ha mer informasjon, kan du se [Vis prediksjonsresultater](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Oppgave 6 – Opprette et segment med kunder med høy risiko for frafall

Når du kjører modellen, opprettes en ny entitet som vises i **Data** > **Enheter**. Du kan opprette et nytt segment basert på enheten som er opprettet av modellen.

1. Velg **Opprett segment** på resultatsiden.

1. Opprett en regel ved å bruke enheten **OOBSubscriptionChurnPrediction**, og definer segmentet:
   - **Felt**: ChurnScore
   - **Operator**: større enn
   - **Verdi**: 0,6

1. Velg **Lagre**, og **Kjør** segmentet.

Du har nå et segment som er dynamisk oppdatert, og som identifiserer kunder med høy frafallsrisiko for denne abonnementsvirksomheten. Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).

> [!TIP]
> Du kan også opprette et segment for en prediksjonsmodell på **Segmenter**-siden ved å velge **Ny** og velge **Opprett fra** > **Intelligens**. Hvis du vil ha mer informasjon, kan du se [Opprett et nytt segment med hurtigsegmenter](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
