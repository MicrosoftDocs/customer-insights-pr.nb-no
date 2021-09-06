---
title: LiveRamp-kobling
description: Lær hvordan du konfigurerer tilkoblingen og eksporten til LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7940db3efacad62ba16099849b3e3ca00d2a5cc1ed31e15a34209c0797e6ae13
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035657"
---
# <a name="export-segments-to-liverampreg-preview"></a>Eksportere segmenter til LiveRamp&reg; (forhåndsvisning)

Aktiver dataene i LiveRamp for å koble til over 500 plattformer på tvers av digitale og sosiale systemer og TV-er. Du kan arbeide med dataene dine i LiveRamp for å målrette, undertrykke og tilpasse annonsekampanjer.

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

- Du må ha et LiveRamp-abonnement for å bruke denne koblingen.
- Hvis du vil ha et abonnement, [kontakter du LiveRamp](https://liveramp.com/contact/) direkte. [Finn ut mer om LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Konfigurere tilkobling til LiveRamp

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **LiveRamp** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi et **brukernavn** og **passord** for din LiveRamp sikker FTP (SFTP)-konto.
Denne legitimasjonen kan være forskjellig fra din LiveRamp Onboarding-legitimasjon.

1. Velg **Bekreft** for å teste tilkoblingen til LiveRamp.

1. Etter vellykket verifisering må du gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra LiveRamp-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. I feltet **Velg nøkkelidentifikator** velger du **E-post**, **Navn og adresse** eller **Telefon** for å sende til LiveRamp for identitetsløsning.
   > [!div class="mx-imgBorder"]
   > ![LiveRamp-kobling med attributtilordning.](media/export-liveramp-segments.png "LiveRamp-kobling med attributtilordning")

1. Tilordne de tilsvarende attributtene fra den enhetlige kundeenheten for den valgte nøkkelidentifikatoren.

1. Velg **Legg til attributt** for å tilordne flere attributter som skal sendes til LiveRamp.

   > [!TIP]
   > Det å sende flere nøkkelidentifikatorattributter til LiveRamp gir deg sannsynligvis en høyere samsvarsrate.

1. Velg segmentene du vil eksportere til LiveRamp.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til LiveRamp, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at LiveRamp oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
