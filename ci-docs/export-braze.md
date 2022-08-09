---
title: Eksporter segmenter til Braze (forhåndsversjon)
description: Finn ut hvordan du konfigurerer og eksporterer til Braze.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 84dc7f13f30e0334d431fe5b5866c7f87e82ab27
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195119"
---
# <a name="export-segments-to-braze-preview"></a>Eksporter segmenter til Braze (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Braze, og bruk dem for markedsføringsaktiviteter.

## <a name="prerequisites"></a>Forutsetning

- En [Braze-konto](https://www.braze.com/) og tilsvarende administratorlegitimasjon.
- En [API-nøkkel for Braze](https://www.braze.com/docs/api/basics/)
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse og en Kunde-ID for Braze.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million kundeprofiler til Braze, som kan ta opptil 40 minutter å eksportere. Antall kundeprofiler du kan eksportere til Braze, avhenger av kontrakten med Braze.
- Bare segmenter.

## <a name="set-up-connection-to-braze"></a>Konfigurere tilkoblingen til Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Braze**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Oppgi API-nøkkelen for Braze for å fortsette å logge på.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Braze-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Velg feltet som representerer kundens Braze-ID i feltet **Kunde-ID**. Segmentene i Braze opprettes med samme navn på segmentet som i Dynamics 365 Customer Insights. Du kan velge flere valgfrie felt for samsvarende data.

1. Velg enhetene eller segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
