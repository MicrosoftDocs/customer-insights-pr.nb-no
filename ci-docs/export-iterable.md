---
title: Eksporter segmenter til Iterable (forhåndsversjon)
description: Finn ut hvordan du konfigurerer og eksporterer til Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195441"
---
# <a name="export-segments-to-iterable-preview"></a>Eksporter segmenter til Iterable (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Iterable, og bruk dem for markedsføringsaktiviteter.

## <a name="prerequisites"></a>Forutsetning

- En [Iterable-konto](https://iterable.com/) og tilsvarende administratorlegitimasjon.
- En [API-nøkkel for Iterable](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million kundeprofiler til Iterable, som kan ta opptil 30 minutter å eksportere. Antall kundeprofiler du kan eksportere til Iterable, avhenger av kontrakten med Iterable.
- Bare segmenter.

## <a name="set-up-connection-to-iterable"></a>Konfigurere tilkoblingen til Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Iterable**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Oppgi API-nøkkelen for Iterable for å fortsette å logge på.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Iterable-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Listen som opprettes i Iterable, får nøyaktig samme navn som segmentnavnet i Dynamics 365 Customer Insights.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
