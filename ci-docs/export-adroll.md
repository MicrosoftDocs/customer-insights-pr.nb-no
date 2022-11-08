---
title: Eksportere segmenter til AdRoll (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 81adad4caf2d4c6f792bf920b29fc7c67eef42b0
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724724"
---
# <a name="export-segments-to-adroll-preview"></a>Eksportere segmenter til AdRoll (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til AdRoll, og bruk dem for reklame.

## <a name="prerequisites"></a>Forutsetning

- En [AdRoll-konto](https://www.adroll.com/) og tilhørende administratorlegitimasjon.
- En [ID for AdRoll-annonsør](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Private Link kombinert med Bring your own storage (BYOS) støttes ikke.
- Opptil 250 000 kundeprofiler til per eksport til AdRoll, som kan ta opptil 10 minutter å fullføre. Antall kundeprofiler du kan eksportere til AdRoll, avhenger av kontrakten med AdRoll.
- Bare segmenter. Et segment må inneholde minst 100 kundeprofiler.

## <a name="set-up-connection-to-adroll"></a>Konfigurer tilkobling til AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **AdRoll**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Godkjenn med AdRoll**, og angi administratorlegitimasjonen din for AdRoll.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra AdRoll-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Angi **ID for AdRoll-annonsør**.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
