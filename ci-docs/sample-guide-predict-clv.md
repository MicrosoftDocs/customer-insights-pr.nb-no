---
title: Eksempelveiledning for prediksjon om kundens levetidsverdi (CLV)
description: Bruk denne eksempelveiledningen til å teste prediksjonsmodellen for kundens levetidsverdi.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609650"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Eksempelveiledning for prediksjon om kundens levetidsverdi (CLV)

Denne veiledningen går gjennom et komplett eksempel på prediksjon om kundens levetidsverdi (CLV) i Customer Insights ved hjelp av eksempeldata. Vi anbefaler at du prøver denne prediksjonen [i et nytt miljø](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso er et selskap som produserer kaffe og kaffemaskiner av høy kvalitet. De selger produktene via nettstedet til Contoso Coffee. Selskapet ønsker å forstå verdien (omsetningen) som kundene kan generere i løpet av de neste 12 månedene. Hvis de vet den forventede verdien kundene kan generere i løpet av de neste 12 månedene, kan de styre markedsføringen mot kunder som genererer høy verdi.

## <a name="prerequisites"></a>Forutsetning

- Minst [bidragsytertillatelser](permissions.md).

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

1. **Lagre** datakilden.

### <a name="ingest-online-purchase-data"></a>Hente inn online kjøpsdata

1. Legge til et nyttdata sett i samme **eCommerce**-datakilde. Velg koblingen **Tekst/CSV** på nytt.

1. Skriv inn URL-adressen for **Online kjøp**-dataene https://aka.ms/ciadclassonline.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **PurchasedOn**: Dato/klokkeslett
   - **TotalPrice**: Valuta

1. I **Navn**-feltet i sideruten endrer du navnet på datakilden til **eCommercePurchases**.

1. **Lagre** datakilden.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Hente inn kundedata fra lojalitetsskjema

1. Opprett en datakilde kalt **LoyaltyScheme**, og velg koblingen **Tekst/CSV**.

1. Angi nettadressen til lojalitetskunder: https://aka.ms/ciadclasscustomerloyalty.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltall
   - **CreatedOn**: Dato/klokkeslett

1. I **Navn**-feltet i den høyre ruten endrer du navnet på datakilden til **loyCustomers**.

1. **Lagre** datakilden.

### <a name="ingest-customer-data-from-website-reviews"></a>Hente inn kundedata fra gjennomganger av nettsteder

1. Opprett en datakilde kalt **Website**, og velg koblingen **Tekst/CSV**.

1. Angi nettadressen til anmeldelser av nettsteder: https://aka.ms/CI-ILT/WebReviews.

1. Når du redigerer dataene, velger du **Transformasjon** og deretter **Bruk første rad som overskrifter**.

1. Oppdater datatypen for kolonnene som vises nedenfor:
   - **ReviewRating**: Desimaltall
   - **ReviewDate**: Dato

1. I **Navn**-feltet i ruten til høyre endrer du navnet på datakilden til **Reviews**.

1. **Lagre** datakilden.

## <a name="task-2---data-unification"></a>Oppgave 2 – Dataforening

Gå gjennom artikkelen [om datasamling](data-unification.md). Følgende informasjon forutsetter at du er fortrolig med datasamling generelt.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Oppgave 3 – opprett aktivitet for transaksjonslogg

Se gjennom artikkelen [om kundeaktiviteter](activities.md). Følgende informasjon forutsetter at du er fortrolig med opprettelse av aktiviteter generelt.

1. Opprett en aktivitet kalt **eCommercePurchases** med enheten *eCommercePurchases:eCommerce* og primærnøkkelen for den, **PurchaseId**.

1. Opprett en relasjon mellom *eCommercePurchases:eCommerce* og *eCommerceContacts:eCommerce* med **ContactID** som sekundærnøkkelen for å koble sammen de to enhetene.

1. Velg **TotalPrice** for **EventActivity** og **PurchasedOn** for **TimeStamp**.

1. Velg **SalesOrderLine** for **Aktivitetstype**, og tilordne aktivitetsdataene semantisk.

1. Kjør aktiviteten.

1. Legg til en ny aktivitet, og tilordne feltnavnene til de tilsvarende feltene:
   - **Aktivitetsenhet**: Reviews:Website
   - **Primærnøkkel**: ReviewId
   - **Tidsstempel**: ReviewDate
   - **Hendelsesaktivitet**: ActivityTypeDisplay
   - **Tilleggsdetaljer**: ReviewRating
   - **Aktivitetstype**: Review

1. Kjør aktiviteten.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Oppgave 4 – konfigurere prediksjon om kundens levetidsverdi

Når de enhetlige kundeprofilene er på plass og aktiviteten opprettet, kjører du prediksjonen om kundens levetidsverdi (CLV). Hvis du vil ha detaljerte trinn, kan du se [Prediksjon av kundens levetidsverdi](predict-customer-lifetime-value.md).

1. Gå til **Intelligens** > **Prediksjoner**.

1. Velg **Bruk modell** på flisen **Kundens levetidsverdi** i **Opprett**-fanen.

1. Velg **Komme i gang**.

1. Gi modellen navnet **OOB eCommerce CLV Prediction** og utdataenheten **OOBeCommerceCLVPrediction**.

1. Definer modellinnstillinger:
   - **Tidsperiode for prediksjon**: **12 måneder eller 1 år** for å definere hvor langt inn i fremtiden CLV skal forutsies.
   - **Aktive kunder**: **La modell beregne kjøpsintervall** som er tidsrammen der en kunde må ha hatt minst én transaksjon for å bli betraktet som aktiv.
   - **Kunder med høy verdi**: Definer kunder med høy verdi manuelt som **de mest aktive 30 % av aktive kunder**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Innstillinger-trinnet i veiledningen for CLV-modellen.":::

1. Velg **Neste**.

1. I trinnet **Obligatoriske data** velger du **Legg til data** for å oppgi transaksjonshistorikkdataene.

    :::image type="content" source="media/clv-model-required.png" alt-text="Trinnet Legg til obligatoriske data i veiledningen for CLV-modellen.":::

1. Velg **SalesOrderLine** og enheten eCommercePurchases, og velg **Neste**. De obligatoriske dataene blir automatisk fylt ut fra aktiviteten. Velg **Lagre** og deretter **Neste**.

1. Trinnet **Tilleggsdata (valgfritt)** lar deg legge til flere kundeaktivitetsdata for å få mer innsikt for kundesamhandlinger. I dette eksemplet velger du **Legg til data** og legger til nettanmeldelsesaktiviteten.

1. Velg **Neste**.

1. Velg **Månedlig** for modelltidsplanen i **Dataoppdateringer**.

1. Velg **Neste**.

1. Når du har sett gjennom alle detaljene, velger du **Lagre og kjør**.

## <a name="task-5---review-model-results-and-explanations"></a>Oppgave 5 – gå gjennom modellresultater og forklaringer

La modellen fullføre opplæringen og beregne poengsum for dataene. Gå gjennom [resultatene og forklaringene av CLV-modellen](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Oppgave 6 – opprette et segment for kunder med høy verdi

Når du kjører modellen, opprettes en ny entitet som vises i **Data** > **Enheter**. Du kan opprette et nytt kundesegment basert på enheten som ble opprettet av modellen.

1. Velg **Opprett segment** på resultatsiden.

1. Opprett en regel ved å bruke enheten **OOBeCommerceCLVPrediction**, og definer segmentet:
   - **Felt**: CLVScore
   - **Operator**: større enn
   - **Verdi**: 1500

1. Velg **Lagre**, og **Kjør** segmentet.

Du har nå et segment som identifiserer kunder som er anslått å generere mer enn USD 1500 i omsetning de neste 12 månedene. Dette segmentet oppdateres dynamisk hvis mer data tas inn. Hvis du vil ha mer informasjon, kan du se [Opprette og behandle segmenter](segments.md).

> [!TIP]
> Du kan også opprette et segment for en prediksjonsmodell på **Segmenter**-siden ved å velge **Ny** og velge **Opprett fra** > **Intelligens**. Hvis du vil ha mer informasjon, kan du se [Opprett et nytt segment med hurtigsegmenter](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
