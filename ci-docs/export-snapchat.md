---
title: Eksportere segmenter til Snapchat (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195394"
---
# <a name="export-segments-to-snapchat-preview"></a>Eksportere segmenter til Snapchat (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Snapchat, og bruk dem til reklame.

## <a name="prerequisites"></a>Forutsetning

- En [Snapchat-forretningskonto](https://business.snapchat.com/), en [Snapchat-annonsekonto](https://ads.snapchat.com/) og tilsvarende administratorlegitimasjon. Du må minst være medlem av en organisasjonskonto og dataansvarlig for en bestemt annonsekonto.
- Minst én målgruppe i Snapchat Audience Manager av typen SAM (Snap Audience Match).
- [ID-en for Snapchat-segmentet/-målgruppen](https://businesshelp.snapchat.com/s/article/custom-audiences). ID-en for målgruppe finner du i nettadressen etter at du har valgt målgruppe Snapchat Audience Manager.
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million kundeprofiler, som kan ta opptil 15 minutter å eksportere.
- Bare segmenter.

## <a name="set-up-connection-to-snapchat"></a>Konfigurere tilkobling til Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Snapchat**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Godkjenn med Snapchat**, og angi legitimasjonen for administrator for Snapchat.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Snapchat-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Angi **ID for Snapchat-segment/-målgruppe**.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
