---
title: Eksportere Customer Insights-data til SFTP-verter (inneholder video)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til en SFTP-plassering.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7b09da093d6332c5081da1beadc1df59f63c31d2
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231166"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Eksportere segmenter og andre data til SFTP (forhåndsversjon)

Bruk kundedataene i tredjepartsprogrammer ved å eksportere dem til en plassering i Secure File Transfer Protocol (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Forutsetninger for tilkobling

- Tilgjengelighet av en SFTP-vert og tilsvarende legitimasjon.

## <a name="known-limitations"></a>Kjente begrensninger

- SFTP-mål bak brannmurer støttes for øyeblikket ikke. 
- Kjøretiden for en eksport avhenger av systemytelsen. Vi anbefaler to CPU-kjerner og 1 GB minne som minimal konfigurasjon av serveren. 
- Det kan ta tre timer å eksportere enheter med opptil 100 millioner kundeprofiler når du bruker den anbefalte minimumskonfigurasjonen av to CPU-kjerner og 1 GB minne. 

## <a name="set-up-connection-to-sftp"></a>Konfigurer tilkobling til SFTP

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **SFTP** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi et **brukernavn**, et **passord** og et **vertsnavn** og **eksportmappe** for SFTP-kontoen.

1. Velg **Bekreft** for å teste tilkoblingen.

1. Velg om du vil eksportere dataene **Komprimert** eller **Pakket ut** og **feltskilletegnet** for de eksporterte filene.

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra SFTP-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Velg enhetene du vil eksportere, for eksempel segmenter.

   > [!NOTE]
   > Hver valgte enhet blir delt opp i opptil fem utdatafiler når de eksporteres. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data via SFTP, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at eksportmålet oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
