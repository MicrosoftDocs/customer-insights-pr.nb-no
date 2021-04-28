---
title: Eksportere Customer Insights-data til Mailchimp
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759890"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a>Eksportere segmentlister til Mailchimp (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til MailChimp for å opprette nyhetsbrev og e-postkampanjer.

## <a name="prerequisites-for-connection"></a>Forutsetninger for tilkobling

-   Du har en [Mailchimp-konto](https://mailchimp.com/) og tilhørende påloggingsinformasjon for administrator.
-   Det finnes eksisterende målgrupper i Mailchimp og de tilsvarende ID-ene. Hvis du vil ha mer informasjon, kan du se [målgrupper i Mailchimp](https://mailchimp.com/help/create-audience/).
-   Du har [konfigurerte segmenter](segments.md)
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million profiler per eksport til Mailchimp.
- Eksport til Mailchimp er begrenset til segmenter.
- Det kan ta opptil tre timer å eksportere segmenter med 1 million profiler. 
- Antallet profiler du kan eksportere til Mailchimp, er avhengig av og begrenset til kontrakten din med Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Konfigurer tilkoblingen til Mailchimp

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Autopilot** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Mailchimp.

1. Velg **Godkjenn med Mailchimp**, og angi Mailchimp-legitimasjonen din.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen. 

## <a name="configure-the-connector"></a>Konfigurere koblingen

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data**> **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Mailchimp-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi **[ID for Mailchimp-målgruppe](https://mailchimp.com/help/find-audience-id/)**

3. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. 

1. Du kan eventuelt eksportere **fornavn** og **etternavn** for å opprette mer tilpassede e-poster. Velg **Legg til attributt** for å tilordne disse feltene.

1. Velg segmentene du vil eksportere. Du kan eksportere opptil 1 million kundeprofiler totalt til Mailchimp.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Mailchimp, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Mailchimp oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
