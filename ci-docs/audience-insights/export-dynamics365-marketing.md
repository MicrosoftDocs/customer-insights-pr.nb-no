---
title: Eksportere Customer Insights-data til Dynamics 365 Marketing
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bd8189f8daee1a6aea75e75e116186f62a360ba4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692493"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Bruke segmenter i Dynamics 365 Marketing (forhåndsversjon)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Bruk [segmenter](segments.md) til å generere kampanjer og kontakte spesifikke grupper med kunder med Dynamics 365 Marketing. Hvis du vil ha mer informasjon, kan du se [Bruke segmenter fra Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite-for-a-connection"></a>Forutsetninger for en tilkobling

- Kontaktoppføringer må finnes i Dynamics 365 Marketing før du kan eksportere et segment fra Customer Insights til Marketing. Les mer om hvordan du inntar kontakter i [Dynamics 365 Marketing ved hjelp av Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > Hvis du eksporterer segmenter fra målgruppeinnsikt til Marketing, opprettes ikke nye kontaktoppføringer i Marketing-forekomstene. Kontaktoppføringene fra Marketing må legges inn i målgruppeinnsikt og brukes som en datakilde. De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.

## <a name="set-up-connection-to-marketing"></a>Konfigurere tilkobling til Marketing

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Dynamics 365 Marketing** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Skriv inn organisasjonens URL-adresse for Marketing i **Serveradresse**-feltet.

1. I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Marketing-konto.

1. Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.

1. Velg **Lagre** for å fullføre tilkoblingen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Dynamics 365 Marketing-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Velg ett eller flere segmenter.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
