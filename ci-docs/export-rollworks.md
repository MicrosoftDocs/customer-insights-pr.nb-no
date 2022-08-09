---
title: Eksportere segmenter til RollWorks (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e13aeca4ee5309f85e7de2986cd1a2ba5d2992fb
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195624"
---
# <a name="export-segments-to-rollworks-preview"></a>Eksportere segmenter til RollWorks (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til RollWorks, og bruk dem til reklame.

## <a name="prerequisites"></a>Forutsetning

- En [RollWorks-konto](https://www.rollworks.com/) og tilhørende administratorlegitimasjon.
- En [ID for RollWorks-annonser](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 250 000 kundeprofiler til per eksport til RollWorks, som kan ta opptil 10 minutter å fullføre. Antall kundeprofiler du kan eksportere til RollWorks, avhenger av kontrakten med RollWorks.
- Bare segmenter.

## <a name="set-up-connection-to-rollworks"></a>Konfigurer tilkoblingen til RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **RollWorks**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen.  Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Godkjenn med RollWorks**, og angi legitimasjonen for administrator for RollWorks.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra RollWorks-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Angi **ID for RollWorks-annonser**.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
