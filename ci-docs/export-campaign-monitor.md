---
title: Eksportere segmenter til Campaign Monitor (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporten til Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196314"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Eksportere segmenter til Campaign Monitor (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Campaign Monitor, og bruk dem for markedsføringsaktiviteter.

## <a name="prerequisites"></a>Forutsetning

- En [Campaign Monitor-konto](https://www.campaignmonitor.com/) og tilhørende administratorlegitimasjon.
- En [ID for Campaign Monitor-liste](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- En [generert API-nøkkel](https://www.campaignmonitor.com/api/getting-started/) fra **Kontoinnstillinger** i Campaign Monitor først for å vise API-liste-ID-en.
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million kundeprofiler per eksport til Campaign Monitor, som kan ta opptil 20 minutter å fullføre. Antall kundeprofiler du kan eksportere til Campaign Monitor, avhenger av kontrakten med Campaign Monitor.
- Bare segmenter.

## <a name="set-up-connection-to-campaign-monitor"></a>Konfigurer tilkoblingen til Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Campaign Monitor**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Campaign Monitor.

1. Velg **Godkjenn med Campaign Monitor**, og angi legitimasjonen for administrator for Campaign Monitor.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport** for å opprette en ny eksport.

1. Velg en tilkobling fra Campaign Monitor-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Angi **ID for Campaign Monitor-liste**.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Det kreves for å eksportere segmenter til Campaign Monitor.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
