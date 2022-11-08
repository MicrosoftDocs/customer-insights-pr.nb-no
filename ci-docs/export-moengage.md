---
title: Eksporter segmenter til MoEngage
description: Finn ut hvordan du konfigurerer og eksporterer til MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725278"
---
# <a name="export-segments-to-moengage-preview"></a>Eksportere segmenter til MoEngage (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til MoEngage, og bruk dem til e-postmarkedsføring i MoEngage.

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

- [MoEngage-konto](https://www.moengage.com/) og tilsvarende administratorlegitimasjon.
- API-nøkkel for MoEngage fra Innstillinger > API i MoEngage.
- [Konfigurerte segmenter](segments.md) i Customer Insights.

## <a name="known-limitations"></a>Kjente begrensninger

- Private Link kombinert med Bring your own storage (BYOS) støttes ikke.
- Opptil 100 000 kundeprofiler per eksport til MoEngage, som kan ta opptil 15 minutter. Antall kundeprofiler du kan eksportere til MoEngage, avhenger av kontrakten med MoEngage.
- Bare segmenter.

## <a name="set-up-connection-to-moengage"></a>Konfigurer tilkobling til MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **MoEngage** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi [Data-API-ID og API-nøkkel for MoEngage](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen til MoEngage.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport** for å opprette en ny eksport.

1. Velg en tilkobling fra MoEngage-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Gjenta de samme trinnene for andre valgfrie felter.

1. Velg segmentene du vil eksportere. Vi oppretter ett eller flere segmenter med samme navn som de valgte segmentene i MoEngage under **Segmenter** > **Egendefinerte segmenter**.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
