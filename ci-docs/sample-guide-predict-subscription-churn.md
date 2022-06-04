---
title: Eksempelveiledning for prognose på abonnementsfrafall
description: Bruk denne eksempelveiledningen til å prøve ut den medfølgende prediksjonsmodellen for abonnementsfrafall.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741423"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Eksempelveiledning for prognose på abonnementsfrafall

Vi tar deg gjennom et helhetlig eksempel på prediksjon av abonnementsfrafall ved å bruke eksempeldataene som vises nedenfor. 

## <a name="scenario"></a>Scenario

Contoso er et firma som produserer kaffe og kaffemaskiner av høy kvalitet, som de kan selge via nettstedet Contoso Coffee. De har nylig startet et abonnementsselskap for kundene for å få kaffe på en jevn basis. Målet deres er å forstå hvilke kunder med abonnement som kanskje vil annullere abonnementet i løpet av de neste månedene. Det å vite hvilke av kundene som har **sannsynlighet for frafall**, kan hjelpe dem med å spare markedsføringsinnsats ved å fokusere på å beholde dem.

## <a name="prerequisites"></a>Forutsetninger

- Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.
- Vi anbefaler at du implementerer følgende trinn [i et nytt miljø](manage-environments.md).

## <a name="task-1---ingest-data"></a>Oppgave 1 – hente inn data

Se særlig gjennom artiklene [om datainntak](data-sources.md) og [import av datakilder ved å bruke Power Query-koblinger](connect-power-query.md). Følgende informasjon forutsetter at du kjenner til datainntakt generelt. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Hente inn kundedata fra eCommerce-plattform

1. Opprett en datakilde med navnet **eCommerce**, velg importalternativet, og velg koblingen **Tekst/CSV**.

1. Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscontacts.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:

   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/klokkeslett/sone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformer fødselsdato til dato.":::

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **eCommerceContacts**

1. Lagre datakilden.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Hente inn kundedata fra lojalitetsskjema

1. Opprett en datakilde med navnet **LoyaltyScheme**, velg importalternativet, og velg koblingen **Tekst/CSV**.

1. Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscustomerloyalty.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:

   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltall
   - **CreatedOn**: Dato/klokkeslett

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **loyCustomers**.

1. Lagre datakilden.

### <a name="ingest-subscription-information"></a>Hente inn informasjon abonnement

1. Opprett en datakilde med navnet **SubscriptionHistory**, velg importalternativet, og velg koblingen **Tekst/CSV**.

1. Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadchurnsubscriptionhistory.

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

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **SubscriptionHistory**.

1. Lagre datakilden.

### <a name="ingest-customer-data-from-website-reviews"></a>Hente inn kundedata fra gjennomganger av nettsteder

1. Opprett en datakilde med navnet **Nettsted**, velg importalternativet, og velg koblingen **Tekst/CSV**.

1. Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasswebsite.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:

   - **ReviewRating**: Whole Heltall
   - **ReviewDate**: Dato

1. I Navn-feltet i den høyre ruten endrer du navnet på datakilden fra **Query** til **webReviews**.

## <a name="task-2---data-unification"></a>Oppgave 2 – Dataforening

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Oppgave 3 – Konfigurere prognosen for abonnementsfrafall

Med de enhetlige kundeprofilene på plass kan vi nå kjøre prediksjonen for abonnementsfrafall. Hvis du vil ha detaljerte trinn, kan du se artikkelen [Prediksjon for abonnementsfrafall](predict-subscription-churn.md). 

1. Gå til **Intelligens** > **Utforsk**, og velg å bruke **kundefrafallsmodellen**.

1. Velg **Abonnement**-alternativet, og velg **Kom i gang**.

1. Gi modellen navnet **Frafallsprognose for OOB-abonnement**, og gi utdataenheten navnet **OOBSubscriptionChurnPrediction**.

1. Definer to betingelser for frafallsmodellen:

   * **Dager siden abonnementet ble avsluttet**: **Minst 60** dager. Hvis en kunde ikke fornyer abonnementet i denne perioden etter at abonnementet er avsluttet, anses de som frafalt. 

   * **Frafallsdefinisjon**: **Minst 93** dager. Hvor lenge modellen forutsier hvilke kunder som kanskje frafaller. Jo lenger inn i fremtiden som du ser, jo mindre nøayktig blir resultatet.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Velg modellbryterne Prediksjonsvindu og Frafallsdefinisjon.":::

1. Velg **Legg til obligatoriske data**, og velg **Legg til data** for abonnementshistorikken.

1. Legg til enheten **Subscription : SubscriptionHistory**, og tilordne feltene fra eCommerce til de tilsvarende feltene som kreves av modellen.

1. Slå sammen enheten **Subscription : SubscriptionHistory** med **eCommerceContacts : eCommerce**, og gi relasjonen navnet **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Slå sammen eCommerce-enheter.":::

1. Under Kundeaktiviteter legger du til enheten **webReviews : Website** og tilordner feltene fra webReviews til de tilsvarende feltene som kreves av modellen. 
   - Primærnøkkel: ReviewId
   - Tidsstempel: ReviewDate
   - Hendelse: ReviewRating

1. Konfigurere en aktivitet for gjennomganger av nettsteder. Velg aktiviteten **Gjennomgang**, og slå sammen enheten **webReviews : Website** med **eCommerceContacts : eCommerce**.

1. Velg **Neste** for å angi modellplanen.

   Modellen må læres opp regelmessig for å lære nye mønstre når nye data er hentet inn. I dette eksemplet velger du **Månedlig**.

1. Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**.

## <a name="task-4---review-model-results-and-explanations"></a>Oppgave 4 – gå gjennom modellresultater og forklaringer

La modellen fullføre opplæringen og beregne poengsum for dataene. Du kan nå se gjennom forklaringer av modellen for abonnementsfrafall. Hvis du vil ha mer informasjon, kan du se [Gå gjennom en prediksjonsstatus og resultater](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Oppgave 5 – Opprette et segment med kunder med høy risiko for frafall

Når du kjører produksjonsmodellen, opprettes det en ny enhet som du kan se i **Data** > **Enheter**.   

Du kan opprette et nytt segment basert på enheten som er opprettet av modellen.

1.  Gå til **Segmenter**. Velg **Ny**, og velg **Opprett fra** > **Intelligens**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Opprette et segment med modellutdataene.":::

1. Velg **OOBSubscriptionChurnPrediction**-endepunktet, og definer segmentet: 
   - Felt: ChurnScore
   - Operator: større enn
   - Verdi: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Konfigurer segement for abonnementsfrafall.":::

Du har nå et segment som er dynamisk oppdatert, og som identifiserer kunder med høy frafallsrisiko for denne abonnementsvirksomheten.

Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]