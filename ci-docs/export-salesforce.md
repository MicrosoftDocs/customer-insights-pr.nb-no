---
title: Eksporter data til Salesforce Marketing Cloud (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081464"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Eksporter data til Salesforce Marketing Cloud (forhåndsversjon)

Bruk kundedataene i Salesforce Marketing Cloud ved å eksportere dem via en SFTP-plassering (Secure File Transfer Protocol).

## <a name="prerequisites-for-connection"></a>Forutsetninger for tilkobling

- Tilgjengelighet av SFTP-vert og tilsvarende administratorlegitimasjon. [Konfigurere SFTP-steder for Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Konfigurere tilkoblingen til Salesforce Marketing Cloud

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Salesforce Marketing Cloud** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi et **brukernavn**, et **passord** og et **vertsnavn** og **eksportmappe** for SFTP-kontoen.

1. Velg **Bekreft** for å teste tilkoblingen.

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra SFTP-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Velg om du vil eksportere dataene **Komprimert** eller **Pakket ut** og **feltskilletegnet** for de eksporterte filene.

1. Velg enhetene du vil eksportere, for eksempel segmenter.

   > [!NOTE]
   > Hver valgte enhet blir delt opp i opptil fem utdatafiler når de eksporteres. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importere Customer Insights-data fra SFTP-sted til Salesforce Marketing Cloud

1. Opprett [datautvidelser i Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) for å importere Customer Insights-datafilen fra SFTP-plasseringen.

2. [Importer dataene fra SFTP-plasseringen](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) til datautvidelsen for Salesforce Marketing Cloud. 

3. Konfigurer automatiseringen til å importere dataene til datautvidelsene. Lær mer om [fildroppingsautomatiseringer og planlagte automatiseringer](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definere [fildroppingsautomatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) eller en [planlagt automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Her er et eksempel på [automatisering med SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data via SFTP, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at eksportmålet oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.

[!INCLUDE [footer-include](includes/footer-banner.md)]
