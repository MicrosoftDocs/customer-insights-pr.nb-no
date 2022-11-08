---
title: Eksportere segmenter til Google Ads (forhåndsvisning)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725090"
---
# <a name="export-segments-to-google-ads-preview"></a>Eksportere segmenter til Google Ads (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til en Google Ads-målgruppeliste, og bruk dem til å annonsere på Google Search, Gmail og YouTube og Google Displaynettverk.

## <a name="prerequisites"></a>Forutsetning

- En [Google Ads-konto](https://ads.google.com/) og tilhørende påloggingsinformasjon for administrator.
- En [Kunde-ID for Google Ads](https://support.google.com/google-ads/answer/1704344).
- Kravene i [policyen for Customer Match](https://support.google.com/adspolicy/answer/6299717) er oppfylt.
- Kravene til [størrelsene for remarkedsføringsliste](https://support.google.com/google-ads/answer/7558048) er oppfylt.
- [Konfigurerte segmenter](segments.md).
- Unified customer profile i de eksporterte segmentene inneholder felt som representerer e-postadresse, telefon, mobilannonsør-ID, bruker-ID fra tredjepart eller adresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Private Link kombinert med Bring your own storage (BYOS) støttes ikke.
- Eksport av opptil 1 million kundeprofiler per eksport til Google Ads, som kan ta opptil 30 minutter å fullføre på grunn av begrensninger på leverandørsiden.
- Bare segmenter.
- Samsvar i Google Ads kan ta opptil 48 timer.

## <a name="set-up-connection-to-google-ads"></a>Konfigurer tilkobling til Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Google Ads**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi kunde-ID-en for Google Ads.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Godkjenn med Google Ads**, og angi Google Ads-legitimasjonen din.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Google Ads-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg om du vil bruke en eksisterende målgruppe eller opprette en ny:
   - Hvis du vil oppdatere en eksisterende Google Ads-målgruppe, angir du [Google Ads-målgruppe-ID-en](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns)
   - Hvis du vil opprette en ny målgruppe, lar du feltet Google-målgruppe-ID stå tomt. Customer Insights oppretter automatisk en ny målgruppe i Google Ads-kontoen din og bruker navnet på det eksporterte segmentet.

1. Velg ett eller flere datafelt som skal eksporteres, i **Datasamsvar**-delen, og velg feltet som representerer de tilsvarende datafeltene i Customer Insights.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
