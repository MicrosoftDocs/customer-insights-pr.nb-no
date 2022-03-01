---
title: Eksportere Customer Insights-data til Autopilot
description: Lær hvordan du konfigurerer tilkoblingen til Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596143"
---
# <a name="connector-for-autopilot-preview"></a>Kontakt for Autopilot (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Autopilot, og bruk dem for e-postmarkedsføring i Autopilot. 

## <a name="prerequisites"></a>Forutsetninger

-   Du har en [Autopilot-konto](https://www.autopilothq.com/) og tilhørende påloggingsinformasjon for administrator.
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="connect-to-autopilot"></a>Koble til Autopilot

1. Gå til **Admin** > **Eksporter mål**.

1. Under **Autopilot** velger du **Oppsett**.

1. Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurasjonsrute for Autopilot-tilkobling.":::

1. Angi **API-nøkkelen for Autopilot** [API-nøkkel for Autopilot](https://autopilot.docs.apiary.io/#).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Autopilot.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Neste** for å konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurere koblingen

1. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**.

1. Velg segmentene du vil eksportere. Vi **anbefaler på det sterkeste at du ikke eksporterer mer enn 100 000 kundeprofiler totalt** til Autopilot. 

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 100 000 profiler totalt til Autopilot.
- Eksport til Autopilot er begrenset til segmenter.
- Det kan ta opptil noen timer å eksportere opptil 100 000 profiler til Autopilot. 
- Antallet profiler du kan eksportere til Autopilot, er avhengig av og begrenset til kontrakten din med Autopilot.

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Autopilot, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Autopilot oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]