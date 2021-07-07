---
title: Eksempelveiledning for prediksjon for produktanbefaling
description: Bruk denne eksempelveiledningen til å prøve ut den medfølgende prediksjonsmodellen for produktanbefaling.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306178"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Eksempelveiledning for prediksjon for produktanbefaling (forhåndsversjon)

Vi tar deg gjennom et helhetlig eksempel på prediksjon av produktanbefaling ved å bruke eksempeldataene som vises nedenfor.

## <a name="scenario"></a>Scenario

Contoso er et firma som produserer kaffe og kaffemaskiner av høy kvalitet, som de selger via nettstedet sitt, Contoso Coffee. Målet er å forstå hvilke produkter de bør anbefale til sine regelmessige kunder. Hvis du vet hva det er mer **sannsynlig at kundene kjøper**, kan du hjelpe dem med å lagre markedsføringen ved å fokusere på bestemte elementer.

## <a name="prerequisites"></a>Forutsetninger

- Minst [Bidragsyter-tillatelser](permissions.md) i Customer Insights.
- Vi anbefaler at du implementerer følgende trinn [i et nytt miljø](manage-environments.md).

## <a name="task-1---ingest-data"></a>Oppgave 1 – hente inn data

Se gjennom artiklene [om datainntak](data-sources.md) og [importering av datakilder ved hjelp av Power Query-koblinger](connect-power-query.md) spesifikt. Følgende informasjon forutsetter at du kjenner til datainntakt generelt.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Hente inn kundedata fra eCommerce-plattform

1. Opprett en datakilde med navnet **eCommerce**, velg importalternativet, og velg koblingen **Tekst/CSV**.

1. Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscontacts.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/klokkeslett/sone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformer fødselsdato til dato.":::

5. I Navn-feltet i den høyre ruten endrer du navnet på datakilden fra **Query** til **eCommerceContacts**.

6. **Lagre** datakilden.

### <a name="ingest-online-purchase-data"></a>Hente inn online kjøpsdata

1. Legge til et nyttdata sett i samme **eCommerce**-datakilde. Velg koblingen **Tekst/CSV** på nytt.

1. Skriv inn URL-adressen for **Online kjøp**-dataene https://aka.ms/ciadclassonline.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **PurchasedOn**: Dato/klokkeslett
   - **TotalPrice**: Valuta

1. I **Navn**-feltet i sideruten endrer du navnet på datakilden fra **Spørring** til **eCommercePurchases**.

1. **Lagre** datakilden.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Hente inn kundedata fra lojalitetsskjema

1. Opprett en datakilde med navnet **LoyaltyScheme**, velg importalternativet, og velg koblingen **Tekst/CSV**.

1. Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/ciadclasscustomerloyalty.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltall
   - **CreatedOn**: Dato/klokkeslett

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden fra **Spørring** til **loyCustomers**.

1. **Lagre** datakilden.

## <a name="task-2---data-unification"></a>Oppgave 2 – Dataforening

Etter å ha tatt inn dataene begynner vi nå dataforeningsprosessen for å opprette en enhetlig kundeprofil. Hvis du vil ha mer informasjon, kan du se [Dataforening](data-unification.md).

### <a name="map"></a>Tilordne

1. Etter at du har hentet inn dataene, tilordner du kontakter fra eCommerce og lojalitetsdata til vanlige datatyper. Gå til **Data** > **Samle** > **Tilordne**.

2. Velg enhetene som representerer kundeprofilen – **eCommerceContacts** og **loyCustomers**.

   ![Samle ecommerce- og lojalitetsdatakildene.](media/unify-ecommerce-loyalty.png)

3. Velg **ContactId** som primærnøkkelen for **eCommerceContacts** og **LoyaltyID** som primærnøkkelen for **loyCustomers**.

   ![Samle LoyaltyId som primærnøkkel.](media/unify-loyaltyid.png)

### <a name="match"></a>Treff

1. Gå til **Samsvar**-fanen, og velg **Angi rekkefølge**.

2. I rullegardinlisten **Primær** velger du **eCommerceContacts: eCommerce** som hovedkilde , og inkluder alle oppføringer.

3. I nedtrekkslisten **Enhet 2** velger du **loyCustomers: LoyaltyScheme** og inkluderer alle oppføringer.

   ![Samle treff for eCommerce og lojalitet.](media/unify-match-order.png)

4. Velg **Opprett en ny regel**.

5. Legg til din første betingelse ved å bruke FullName.

   - For eCommerceContacts velger du **FullName** i rullegardinlisten.
   - For loyCustomers velger du **FullName** i rullegardinlisten.
   - Velg rullegardinlisten **Normaliser**, og velg **Type (telefon, navn, adresse ...)**.
   - Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.

6. Angi navnet **FullName, Email** for den nye regelen.

   - Legg til en ny betingelse for e-postadresse ved å velge **Legg til betingelse**.
   - Velg **E-post** i rullegardinmenyen for enheten eCommerceContacts.
   - Velg **E-post** i rullegardinmenyen for enheten loyCustomers.
   - La Normaliser være tomt.
   - Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.

   ![Regel for å samle treff for navn og e-post.](media/unify-match-rule.png)

7. Velg **Lagre** og **Kjør**.

### <a name="merge"></a>Flett

1. Gå fil fanen **Slå sammen**.

1. På **ContactId** for enheten **loyCustomers** endrer du visningsnavnet til **ContactIdLOYALTY** for å skille de fra de andre ID-ene som er hentet inn.

   ![Endre navn på contactid fra loyalty id.](media/unify-merge-contactid.png)

1. Velg **Lagre** og **Kjør** for å starte sammenslåingsprosessen.

## <a name="task-3---configure-product-recommendation-prediction"></a>Oppgave 3 – Konfigurer prediksjon av produktanbefaling

Med de enhetlige kundeprofilene på plass kan vi nå kjøre prediksjonen for abonnementsfrafall.

1. Gå til **Intelligens** > **Prediksjon** og velg **Produktanbefaling**.

1. Velg **Komme i gang**.

1. Gi modellen navnet **Prediksjon for OOB-produktanbefalingsmodell** og utdataenheten **OOBProductRecommendationModelPrediction**.

1. Definer tre betingelser for modellen:

   - **Antall produkter**: Angi **5** for denne verdien. Denne innstillingen definerer hvor mange produkter du vil anbefale til kundene.

   - **Forventet å gjenta innkjøp**: Velg **Ja** for å angi at du vil ta med produkter som kundene har kjøpt tidligere, i anbefalingen.

   - **Tilbakeblikksvindu:** Velg minst **365 dager**. Denne innstillingen definerer hvor langt modellen skal se bakover for å se på kundens aktivitet og bruke det som inndata i anbefalingene.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modellinnstillinger for produktanbefalingsmodellen.":::

1. Velg **Obligatoriske data**, og velg **Legg til data** for kjøpshistorikken.

1. Legg til enheten **eCommercePurchases : eCommerce**, og tilordne feltene fra eCommerce til de tilsvarende feltene som kreves av modellen.

1. Slå sammen enheten **eCommercePurchases : eCommerce** med **eCommerceContacts : eCommerce**.

   ![Slå sammen eCommerce-enheter.](media/model-purchase-join.png)

1. Velg **Neste** for å angi modellplanen.

   Modellen må læres opp regelmessig for å lære nye mønstre når nye data er hentet inn. I dette eksemplet velger du **Månedlig**.

1. Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**.


## <a name="task-4---review-model-results-and-explanations"></a>Oppgave 4 – gå gjennom modellresultater og forklaringer

La modellen fullføre opplæringen og beregne poengsum for dataene. Du kan nå se gjennom forklaringer av modellen for produktanbefaling. Hvis du vil ha mer informasjon, kan du se [Gå gjennom en prediksjonsstatus og resultater](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Oppgave 5 – Opprett et segment av mye kjøpte produkter

Når du kjører produksjonsmodellen, opprettes det en ny enhet som du kan se i **Data** > **Enheter**.

Du kan opprette et nytt segment basert på enheten som er opprettet av modellen.

1. Gå til **Segmenter**. Velg **Ny**, og velg **Opprett fra** > **Intelligens**.

   ![Opprette et segment med modellutdataene.](media/segment-intelligence.png)

1. Velg **OOBProductRecommendationModelPrediction**-endepunktet, og definer segmentet:

   - Felt: ProductID
   - Operator: Verdi
   - Verdi: Velg de tre mest populære produkt-ID-ene

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Opprett et segment fra modellresultatene.":::

Du har nå et segment som oppdateres dynamisk, og denne identifiserer kundene som er mer villige til å kjøpe de tre mest anbefalte produktene 

Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
