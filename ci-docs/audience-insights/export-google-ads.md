---
title: Eksportere Customer Insights-data til Google Ads
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523812"
---
# <a name="export-segments-to-google-ads-preview"></a>Eksportere segmenter til Google Ads (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til en Google Ads-målgruppeliste, og bruk dem til å annonsere på Google Search, Gmail og YouTube og Google Displaynettverk. 


## <a name="prerequisites-for-connection"></a>Forutsetninger for tilkobling

-   Du har en [Google Ads-konto](https://ads.google.com/) og tilhørende påloggingsinformasjon for administrator.
-   Du oppfyller kravene i [kundesamsvarspolicyen](https://support.google.com/adspolicy/answer/6299717).
-   Du oppfyller kravene i [størrelsene for remarkedsføringsliste](https://support.google.com/google-ads/answer/7558048).
-   Du har [konfigurerte segmenter](segments.md).
-   Unified customer profile i de eksporterte segmentene inneholder felt som representerer e-postadresse, telefon, mobilannonsør-ID, bruker-ID fra tredjepart eller adresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Eksport til Google Ads er begrenset til segmenter.
- Eksport av segmenter med totalt 1 million kundeprofiler kan ta opptil 30 minutter på grunn av begrensninger på leverandørsiden. 
- Samsvaret i Google Ads kan ta opptil 48 timer.

## <a name="set-up-connection-to-google-ads"></a>Konfigurer tilkobling til Google Ads

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Google Ads** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **[kunde-ID-en for Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Godkjenn med Google Ads**, og angi Google Ads-legitimasjonen din.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Google Ads-delen i feltet **Tilkobling for eksport**. Hvis navnet på denne delen ikke vises, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Hvis du vil opprette en ny målgruppe, lar du feltet Google-målgruppe-ID stå tomt. Vi oppretter automatisk en ny målgruppe i Google Ads-kontoen din og bruker navnet på det eksporterte segmentet. Hvis du vil oppdatere en eksisterende Google Ads-målgruppe, angir du [Google Ads-målgruppe ID-en](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. Velg ett eller flere datafelt som skal eksporteres, i **Datasamsvar**-delen, og velg feltet som representerer de tilsvarende datafeltene i Customer Insights.

1. Velg segmentene du vil eksportere. 

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). 

Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Google Ads, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Google Ads oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
