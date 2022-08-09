---
title: Eksporter data til Salesforce Marketing Cloud (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197050"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Eksporter data til Salesforce Marketing Cloud (forhåndsversjon)

Bruk kundedataene i Salesforce Marketing Cloud ved å eksportere dem via en SFTP-plassering (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Forutsetning

- En [SFTP-vert for Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) og tilsvarende administratorlegitimasjon.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Konfigurer tilkobling til Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Salesforce Marketing Cloud**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi et **brukernavn**, et **passord** og et **vertsnavn** og **eksportmappe** for SFTP-kontoen.

1. Velg **Bekreft** for å teste tilkoblingen.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra SFTP-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg om du vil eksportere dataene **Komprimert** eller **Pakket ut** og **feltskilletegnet** for de eksporterte filene.

1. Velg enhetene du vil eksportere, for eksempel segmenter.

   > [!NOTE]
   > Hver valgte enhet blir delt opp i maks. fem utdatafiler når de eksporteres.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importere Customer Insights-data fra SFTP-sted til Salesforce Marketing Cloud

1. Opprett [datautvidelser i Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) for å importere Customer Insights-datafilen fra SFTP-plasseringen.

2. [Importer dataene fra SFTP-plasseringen](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) til datautvidelsen for Salesforce Marketing Cloud.

3. Konfigurer automatiseringen til å importere dataene til datautvidelsene. Lær mer om [fildroppingsautomatiseringer og planlagte automatiseringer](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definere [fildroppingsautomatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) eller en [planlagt automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Her er et eksempel på [automatisering med SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
