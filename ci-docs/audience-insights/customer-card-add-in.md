---
title: Installere og konfigurere Kundekort-tillegget
description: Installere og konfigurere tillegg for kundekort for Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644055"
---
# <a name="customer-card-add-in-preview"></a>Tillegg for kundekort (forhåndsversjon)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Få en 360-graders visning av kundene direkte i Dynamics 365-apper. Vis demografi, innsikt og timeplan for aktiviteter med kundekorttillegget.

## <a name="prerequisites"></a>Forutsetninger

- Dynamics 365-appen (for eksempel Salgssenter eller Kundeservicehub) versjon 9.0 og nyere med Enhetlig grensesnitt aktivert.
- Kundeprofiler [hentet fra Dynamics 365-appen ved hjelp av Common Data Service](connect-power-query.md).
- Brukere av Kundekort-tillegget må [legges til som brukere](permissions.md) i målgruppeinnsikt.
- [Konfigurerte søke- og filterfunksjoner](search-filter-index.md).
- Demografisk kontroll: Demografiske felt, for eksempel alder eller kjønn, er tilgjengelige i den enhetlige kundeprofilen.
- Suppleringskontroll: Krever at aktive [suppleringer](enrichment-hub.md) er brukt på kundeprofiler.
- Intelligenskontroll: Krever data generert ved hjelp av Azure Machine Learning ([prediksjoner](predictions.md) eller [egendefinerte modeller](custom-models.md))
- Målkontroll: Krever [konfigurerte mål](measures.md).
- Tidslinjekontroll: Krever [konfigurerte aktiviteter](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installere tillegget Kundekort

Kundekorttillegget er en løsning for Customer Engagement-apper i Dynamics 365. Gå til AppSource og søk etter **Dynamics-kundekort** for å installere løsningen. Velg [Tillegg for kundekort på AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) og velg **Hent det nå**.

Det kan hende at du må logge på med administratorlegitimasjonen for Dynamics 365-appen for å kunne installere løsningen.

Det kan ta litt tid før løsningen installeres i miljøet ditt.

## <a name="configure-the-customer-card-add-in"></a>Konfigurere tillegget for kundekort

1. Som administrator kan du gå til delen **Innstillinger** i Dynamics 365 og velge **Løsninger**.

1. Velg **Visningsnavn**-koblingen for løsningen **Dynamics 365 Customer Insights-kundekorttillegg (forhåndsversjon)**.

   > [!div class="mx-imgBorder"]
   > ![Velg visningsnavn](media/select-display-name.png "Velg visningsnavn")

1. Velg **Logg på**, og angi legitimasjonen for administratorkontoen du bruker til å konfigurere Customer Insights.

   > [!NOTE]
   > Kontroller at popup-blokkeringen i nettleseren ikke blokkerer godkjenningsvinduet når du velger knappen **Logg på**.

1. Velg miljøet du vil hente data fra.

1. Definerer hvilke felt som skal tilknyttes oppføringer i Dynamics 365-appen.
   - Hvis du vil tilordne med en kontakt, velger du feltet i kundeenheten som samsvarer med ID-en til kontaktenheten.
   - Hvis du vil tilordne med en forretningsforbindelse, velger du feltet i kundeenheten som samsvarer med ID-en til forretningsforbindelsesenheten.

   > [!div class="mx-imgBorder"]
   > ![Kontakt-ID-felt](media/contact-id-field.png "Kontakt-ID-felt")

1. Velg **Lagre konfigurasjon** for å lagre innstillingene.

1. Deretter må du tilordne sikkerhetsroller i Dynamics 365 slik at brukere kan tilpasse og se kundekortet. I Dynamics 365 går du til **Innstillinger** > **Sikkerhet** > **Brukere**. Velg brukerne du vil redigere brukerroller for, og velg **Behandle roller**.

1. Tilordne rollen **Korttilpasser for Customer Insights** til brukere som skal tilpasse innholdet som vises på kortet for hele organisasjonen.

## <a name="add-customer-card-controls-to-forms"></a>Legge til Kundekort-kontroller i skjemaer
  
1. Hvis du vil legge til kundekortkontrollene i kontaktskjemaet, går du til **Innstillinger** > **Tilpassinger** i Dynamics 365.

1. Velg **Tilpasse systemet**.

1. Bla til **Kontakt**-enheten, utvid den, og velg deretter **Skjemaer**.

1. Velg kontaktskjemaet du vil legge til kundekortkontrollene i.

    > [!div class="mx-imgBorder"]
    > ![Velg kontaktskjemaet](media/contact-active-forms.png "Velg kontaktskjemaet")

1. Hvis du vil legge til en kontroll, drar du et felt fra **Feltutforsker** i skjemaredigeringsprogrammet til stedet der du vil at kontrollen skal vises.

1. Velg feltet i skjemaet du nettopp la til, og velg deretter **Endre egenskaper**.

1. Gå til kategorien **Kontroller**, og velg **Legg til kontroll**. Velg en av de tilgjengelige egendefinerte kontrollene, og velg **Legg til**.

1. I dialogboksen **Feltegenskaper** fjerner du merket for **Vis etikett i skjemaet**.

1. Velg **Web**-alternativet for kontrollen. For suppleringskontrollen må du velge hvilken suppleringstype du vil skal vises, ved å konfigurere **enrichmentType**-feltet. Du må legge til en separat suppleringskontroll for hver suppleringstype.

1. Velg **Lagre** og **Publiser** for å publisere det oppdaterte kontaktskjemaet.

1. Gå til det publiserte kontaktskjemaet. Du vil se den nylig tillagte kontrollen. Det kan hende du må logge på første gang du bruker den.

1. Hvis du vil tilpasse det du vil vise på den egendefinerte kontrollen, velger du Rediger-knappen øverst i høyre hjørne.