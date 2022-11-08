---
title: Eksporter segmenter til Criteo (forhåndsversjon)
description: Finn ut hvordan du konfigurerer og eksporterer til Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 61435030254638965fbeb7980312e73695416aa2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724801"
---
# <a name="export-segments-to-criteo-preview"></a>Eksporter segmenter til Criteo (forhåndsversjon)

Eksporter segmenter for enhetlige kundeprofiler til å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Criteo.

## <a name="prerequisites"></a>Forutsetning

- En [Criteo Dynamics Retargeting-konto](https://www.criteo.com/login/) og tilsvarende administratorlegitimasjon.
- [Konfigurerte segmenter](segments.md).
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Private Link kombinert med Bring your own storage (BYOS) støttes ikke.
- Opptil 1 million kundeprofiler per eksport til Criteo, som kan ta opptil 30 minutter å fullføre. Antall kundeprofiler du kan eksportere til Criteo, avhenger av kontrakten med Criteo.
- Bare segmenter.

## <a name="set-up-connection-to-criteo"></a>Konfigurere tilkoblingen til Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Criteo**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Godkjenn med Criteo**, og angi administratornavn og legitimasjon for Criteo.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Criteo-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
