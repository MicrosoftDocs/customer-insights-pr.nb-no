---
title: Eksportere Customer Insights-data til Google Ads
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759705"
---
# <a name="export-segments-to-google-ads-preview"></a>Eksportere segmenter til Google Ads (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til Google Ads-målgruppelisten, og bruk dem til å annonsere på Google Search, Gmail, YouTube og Google Display Network. 

## <a name="prerequisites-for-connection"></a>Forutsetninger for tilkobling

-   Du har en [Google Ads-konto](https://ads.google.com/) og tilhørende påloggingsinformasjon for administrator.
-   Du har et [godkjent utviklertoken for Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token) 
-   Du oppfyller kravene i [retningslinjene for kundesamsvar](https://support.google.com/adspolicy/answer/6299717)
-   Du oppfyller kravene i [størrelsene for remarkedsføringsliste](https://support.google.com/google-ads/answer/7558048) 

-   Det finnes eksisterende målgrupper i Google Ads og de tilsvarende ID-ene. Hvis du vil ha mer informasjon, kan du se [målgrupper i Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Du har [konfigurerte segmenter](segments.md)
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder felt som representerer en e-postadresse, et fornavn og et etternavn

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million profiler per eksport til Google Ads.
- Eksport til Google Ads er begrenset til segmenter.
- Eksport av segmenter med totalt 1 million profiler kan ta opptil fem minutter på grunn av begrensninger på leverandørsiden. 
- Samsvaret i Google Ads kan ta opptil 48 timer.

## <a name="set-up-connection-to-google-ads"></a>Konfigurer tilkobling til Google Ads

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Google Ads** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **[kunde-ID-en for Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Skriv inn **[det godkjente utviklertokenet for Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Godkjenn med Google Ads**, og angi Google Ads-legitimasjonen din.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Google Ads-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi **[ID-en for Google Ads-målgruppen](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**, og velg **Koble til** for å initialisere tilkoblingen til Google Ads.

1. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. Gjenta de samme trinnene for feltene **Fornavn** og **Etternavn**.

1. Velg segmentene du vil eksportere. Du kan eksportere opptil 1 million kundeprofiler totalt til Google Ads.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Google Ads, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Google Ads oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
