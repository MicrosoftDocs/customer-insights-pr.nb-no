---
title: Eksportere Customer Insights-data til SendGrid
description: Lær hvordan du konfigurerer tilkoblingen til SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597293"
---
# <a name="connector-for-sendgrid-preview"></a>Kontakt for SendGrid (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til SendGrid-kontaktliser, og bruk dem for kampanjer og e-postmarkedsføring i SendGrid. 

## <a name="prerequisites"></a>Forutsetninger

-   Du har en [SendGrid-konto](https://sendgrid.com/) og tilhørende påloggingsinformasjon for administrator.
-   Det finnes eksisterende kontaktlister i SendGrid og de tilsvarende ID-ene. Hvis du vil ha mer informasjon, kan du se [SendGrid – administrer kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="connect-to-sendgrid"></a>Koble til SendGrid

1. Gå til **Admin** > **Eksporter mål**.

1. Under **SendGrid** velger du **Oppsett**.

1. Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Ruten SendGrid-eksportkonfigurasjon.":::

1. Angi **API-nøkkelen for SendGrid** [API-nøkkel for SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Angi **[ID-en for SendGrid-listen](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til SendGrid.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Neste** for å konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurere koblingen

1. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**, **Land/område**, **Delstat**, **Sted** og **Postnummer**.

1. Velg segmentene du vil eksportere. Vi **anbefaler på det sterkeste at du ikke eksporterer mer enn 100 000 kundeprofiler totalt** til SendGrid. 

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).

## <a name="known-limitations"></a>Kjente begrensninger

- Totalt opptil 100 000 profiler til SendGrid.
- Eksport til SendGrid er begrenset til segmenter.
- Det kan ta opptil noen timer å eksportere opptil 100 000 profiler til SendGrid. 
- Antallet profiler du kan eksportere til SendGrid, er avhengig av og begrenset til kontrakten din med SendGrid.

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til SendGrid, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at SendGrid oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]