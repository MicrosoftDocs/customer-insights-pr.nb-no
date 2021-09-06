---
title: Eksempelveiledning for prediksjon om kundens levetidsverdi
description: Bruk denne eksempelveiledningen til å teste prediksjonsmodellen for kundens levetidsverdi.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 705e159f348e876f8a2a0ad3481608c6dd380df3dd74d7e5dba9dd3bebe25e52
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029503"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Eksempelveiledning for prediksjon om kundens levetidsverdi (CLV)

Denne veiledningen går gjennom et komplett eksempel på prediksjon om kundens levetidsverdi (CLV) i Customer Insights ved hjelp av eksempeldata.

## <a name="scenario"></a>Scenario

Contoso er et selskap som produserer kaffe og kaffemaskiner av høy kvalitet. De selger produktene via nettstedet Contoso Coffee. Selskapet ønsker å forstå verdien (omsetningen) som kundene kan generere i løpet av de neste 12 månedene. Hvis de vet den forventede verdien kundene kan generere i løpet av de neste 12 månedene, kan de styre markedsføringen mot kunder som genererer høy verdi.

## <a name="prerequisites"></a>Forutsetninger

- Du må minst ha [bidragsytertillatelser](permissions.md) i målgruppeinnsikt.
- Vi anbefaler at du implementerer følgende trinn [i et nytt miljø](manage-environments.md).

## <a name="task-1---ingest-data"></a>Oppgave 1 – hente inn data

Se gjennom artiklene [om datainntak](data-sources.md) og [import av datakilder ved hjelp av Power Query-koblinger](connect-power-query.md). Følgende informasjon forutsetter at du kjenner til datainntakt generelt.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Hente inn kundedata fra eCommerce-plattform

1. Opprett en datakilde med navnet **eCommerce**, velg importalternativet, og velg koblingen **Tekst/CSV**.

1. Skriv inn nettadressen for eCommerce-kontakter [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/klokkeslett/sone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformer fødselsdato til dato.":::

1. I Navn-feltet i den høyre ruten endrer du navnet på datakilden fra **Query** til **eCommerceContacts**.

1. **Lagre** datakilden.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Hente inn kundedata fra gjennomganger av nettsteder

1. Opprett en datakilde med navnet **Nettsted**, velg importalternativet, og velg koblingen **Tekst/CSV**.

1. Skriv inn URL-adressen for eCommerce-kontakter https://aka.ms/CI-ILT/WebReviews.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:

   - **ReviewRating**: Desimaltall
   - **ReviewDate**: Dato

1. I Navn-feltet i ruten til høyre endrer du navnet til datakilden fra **Spørring** til **Omtaler**.

1. **Lagre** datakilden.

## <a name="task-2---data-unification"></a>Oppgave 2 – Dataforening

Etter å ha tatt inn dataene begynner vi nå dataforeningsprosessen for å opprette en enhetlig kundeprofil. Hvis du vil ha mer informasjon, kan du se [Dataforening](data-unification.md).

### <a name="map"></a>Tilordne

1. Etter at du har hentet inn dataene, tilordner du kontakter fra eCommerce og lojalitetsdata til vanlige datatyper. Gå til **Data** > **Samle** > **Tilordne**.

1. Velg enhetene som representerer kundeprofilen – **eCommerceContacts** og **loyCustomers**. Velg deretter **Bruk**.

   ![Samle ecommerce- og lojalitetsdatakildene.](media/unify-ecommerce-loyalty.png)

1. Velg **ContactId** som primærnøkkelen for **eCommerceContacts** og **LoyaltyID** som primærnøkkelen for **loyCustomers**.

   ![Samle LoyaltyId som primærnøkkel.](media/unify-loyaltyid.png)

1. Velg **Lagre**.

### <a name="match"></a>Treff

1. Gå til **Samsvar**-fanen, og velg **Angi rekkefølge**.

1. I rullegardinlisten **Primær** velger du **eCommerceContacts: eCommerce** som hovedkilde , og inkluder alle oppføringer.

1. I nedtrekkslisten **Enhet 2** velger du **loyCustomers: LoyaltyScheme** og inkluderer alle oppføringer.

   ![Samle treff for eCommerce og lojalitet.](media/unify-match-order.png)

1. Velg **Legg til regel**.

1. Legg til din første betingelse ved å bruke FullName.

   - For eCommerceContacts velger du **FullName** i rullegardinlisten.
   - For loyCustomers velger du **FullName** i rullegardinlisten.
   - Velg **Normaliser**-rullegardinlisten, og velg **Type (telefon, navn, adresse ...)**.
   - Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.

1. Angi navnet **FullName, Email** for den nye regelen.

   - Legg til en ny betingelse for e-postadresse ved å velge **Legg til betingelse**.
   - Velg **E-post** i rullegardinmenyen for enheten eCommerceContacts.
   - Velg **E-post** i rullegardinmenyen for enheten loyCustomers.
   - La Normaliser være tomt.
   - Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.

   ![Regel for å samle treff for navn og e-post.](media/unify-match-rule.png)

1. Velg **Ferdig**.

1. Velg **Lagre** og **Kjør**.

### <a name="merge"></a>Flett

1. Gå fil fanen **Slå sammen**.

1. På **ContactId** for enheten **loyCustomers** endrer du visningsnavnet til **ContactIdLOYALTY** for å skille de fra de andre ID-ene som er hentet inn.

   ![Endre navn på contactid fra loyalty id.](media/unify-merge-contactid.png)

1. Velg **Lagre** og **Kjør sammenslåings- og nedstrømsprosesser**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Oppgave 3 – konfigurere prediksjon om kundens levetidsverdi

Når de enhetlige kundeprofilene er på plass, kan vi nå kjøre prediksjonen om kundens levetidsverdi. Hvis du vil se detaljerte trinn, kan du se [Prediksjon om kundens levetidsverdi (forhåndsversjon)](predict-customer-lifetime-value.md).

1. Gå til **Intelligens**  > **Prediksjoner**, og velg **Modell for kundens levetidsverdi**.

1. Gå gjennom informasjonen i sideruten, og velg **Start**.

1. Gi modellen navnet **OOB eCommerce CLV Prediction** og utdataenheten **OOBeCommerceCLVPrediction**.

1. Definer modellinnstillinger for CLV-modellen:
   - **Tidsperiode for prediksjon**: **12 måneder eller 1 år**. Denne innstillingen angir hvor langt inn i fremtiden kundens levetidsverdi skal forutsies.
   - **Aktive kunder**: Angi hva aktive kunder betyr for virksomheten din. Angi den historiske tidsrammen en kunde må ha hatt minst én transaksjon i, for å kunne regnes som aktiv. Modellen vil bare forutsi CLV for aktive kunder. Velg mellom å la modellen beregne tidsperioden basert på historiske transaksjonsdata, eller angi en bestemt tidsramme. I denne eksempelveiledningen skal vi **la modellen beregne kjøpsintervall**, som er standardalternativet.
   - **Kunder med høy verdi**: Definer kunder med høy verdi som en persentil av kundene som betaler mest. Modellen bruker disse inndataene til å gi resultater som passer forretningsdefinisjonen din av kunder med høy verdi. Du kan velge å la modellen definere kunder med høy verdi. Den bruker en heuristisk regel som avleder persentilen. Du kan også definere kunder med høy verdi som en persentil av fremtidige kunder som betaler mest. I denne eksempelveiledningen definerer vi kunder med høy verdi manuelt som **de mest betalende 30 % av aktive kunder** og velger **Neste**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Innstillinger-trinnet i veiledningen for CLV-modellen.":::

1. I trinnet **Obligatoriske data** velger du **Legg til data** for å oppgi transaksjonshistorikkdataene.

1. Legg til enheten **eCommercePurchases : eCommerce**, og tilordne attributtene som kreves av modellen:
   - Transaksjons-ID: eCommerce.eCommercePurchases.PurchaseId
   - Transaksjonsdato: eCommerce.eCommercePurchases.PurchasedOn
   - Transaksjonsbeløp: eCommerce.eCommercePurchases.TotalPrice
   - Produkt-ID: eCommerce.eCommercePurchases.ProductId

1. Velg **Neste**.

1. Konfigurer relasjonen mellom enheten **eCommercePurchases : eCommerce** og **eCommerceContacts : eCommerce**.

1. Trinnet **Tilleggsdata (valgfritt)** lar deg legge til flere kundeaktivitetsdata. Disse dataene kan gi større innsikt i kundesamhandlinger med virksomheten din, som kan bidra til CLV. Hvis du legger til viktige kundesamhandlinger, for eksempel blogger, kundeservicelogger eller fordelsprogramhistorikk, kan du forbedre nøyaktigheten til prediksjoner. Velg **Legg til data** for å ta med flere kundeaktivitetsdata.

1. Legg til enheten for kundeaktivitet og tilordne feltnavnene til de tilsvarende feltene som kreves av modellen:
   - Enhet for kundeaktivitet: Reviews:Website
   - Primærnøkkel: Website.Reviews.ReviewId
   - Tidsstempel: Website.Reviews.ReviewDate
   - Hendelse (aktivitetsnavn): Website.Reviews.ActivityTypeDisplay
   - Detaljer (beløp eller verdi): Website.Reviews.ReviewRating

1. Velg **Neste**, og konfigurer aktiviteten og relasjonen mellom transaksjonsdataene og kundedataene:  
   - Aktivitetstype: Velg eksisterende
   - Aktivitetsetikett: Review
   - Tilsvarende etikett: Website.Reviews.UserId
   - Kundeenhet: eCommerceContacts:eCommerce
   - Relasjon: WebsiteReviews

1. Velg **Neste** for å angi modellplanen.

   Modellen må læres opp regelmessig for å lære nye mønstre når nye data tas inn. I dette eksemplet velger du **Månedlig**.

1. Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**.

## <a name="task-4---review-model-results-and-explanations"></a>Oppgave 4 – gå gjennom modellresultater og forklaringer

La modellen fullføre opplæringen og beregne poengsum for dataene. Du kan deretter se gjennom resultatene og forklaringene av CLV-modellen. Hvis du vil ha mer informasjon, kan du se [Gå gjennom en prediksjonsstatus og resultater](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Oppgave 5 – opprette et segment for kunder med høy verdi

Når du kjører modellen, opprettes en ny entitet som vises i **Data** > **Enheter**. Du kan opprette et nytt kundesegment basert på enheten som ble opprettet av modellen.

1. Gå til **Segmenter**. 

1. Velg **Ny**, og velg **Opprett fra** > **Intelligens**.

   ![Opprette et segment med modellutdataene.](media/segment-intelligence.png)

1. Velg enheten **OOBeCommerceCLVPrediction**, og definer segmentet:
  - Felt: CLVScore
  - Operator: større enn
  - Verdi: 1500

1. Velg **Se gjennom** og **Lagre** segmentet.

Du har nå et segment som identifiserer kunder som er anslått å generere mer enn USD 1500 i omsetning de neste 12 månedene. Dette segmentet oppdateres dynamisk hvis mer data tas inn.

Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).
