---
title: Eksportere segmenter til Microsoft Advertising (forhåndsversjon)
description: Finn ut hvordan du konfigurerer tilkoblingen og eksporten til Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196544"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Eksportere segmenter til Microsoft Advertising (forhåndsversjon)

Eksporter Customer Insights-segmenter til Microsoft Advertising for å opprette Customer Match-målgrupper. Bruk disse målgruppene for annonsekampanjene.

## <a name="prerequisites"></a>Forutsetning

- En [Microsoft Advertising-konto](https://ads.microsoft.com/) og tilhørende administratorlegitimasjon.
- Kunde-ID og konto-ID for Microsoft Advertising. Finn kunde-ID-en (`cid`) og konto-ID-en (`aid`) i parameterne for nettadressen når du er logget på Microsoft Advertising.
- Vilkårene for bruk for Customer Match er godtatt.
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 500 000 kundeprofiler per eksport til Microsoft Advertising, som kan ta opptil 10 minutter.
- Bare segmenter.

## <a name="set-up-connection-to-microsoft-advertising"></a>Konfigurer tilkobling til Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling** og velg **Microsoft Advertising**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Standarden er administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **Kunde-ID for Microsoft Advertising**.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Godkjenn med Microsoft Advertising**, og angi legitimasjonen for administrator for Microsoft Advertising.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Microsoft Advertising-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg segmentene som skal eksporteres. Customer Match-målgruppene i Microsoft Advertising opprettes automatisk med navnet på segmentene som er valgt for eksport. Hvert segment fører til en egen Customer Match-målgruppe.

1. Angi **Kunde-ID og konto-ID for Microsoft Advertising**.

1. Velg feltet med e-postadressen til en kunde, i delen **Datasamsvar** i **E-post**-feltet.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
