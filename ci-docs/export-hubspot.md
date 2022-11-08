---
title: Eksportere Customer Insights-data til HubSpot
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725366"
---
# <a name="export-segments-to-hubspot-preview"></a>Eksportere segmenter til HubSpot (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til HubSpot, og bruk dem for e-postmarkedsføring.

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

- Du har en [HubSpot-konto](https://www.hubspot.com/) og tilhørende påloggingsinformasjon for administrator.
- [API-nøkkel](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) fra HubSpot.
- [Konfigurerte segmenter](segments.md) i Customer Insights.

## <a name="known-limitations"></a>Kjente begrensninger

- Private Link kombinert med Bring your own storage (BYOS) støttes ikke.
- Opptil 100 000 kundeprofiler per eksport til HubSpot, noe som kan ta opptil 15 minutter å fullføre. Antall kundeprofiler du kan eksportere til HubSpot, avhenger av og begrenses til kontrakten med HubSpot.
- Bare segmenter.

## <a name="set-up-connection-to-hubspot"></a>Konfigurere tilkobling til HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **HubSpot** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi HubSpot-legitimasjon når du blir bedt om det.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen til HubSpot.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport** for å opprette en ny eksport.

1. Velg en tilkobling fra HubSpot-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Gjenta de samme trinnene for andre valgfrie felter.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
