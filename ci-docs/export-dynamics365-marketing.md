---
title: Eksportere Customer Insights-data til Dynamics 365 Marketing
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646483"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Bruke segmenter i Dynamics 365 Marketing (forhåndsversjon)



Bruk [segmenter](segments.md) til å generere kampanjer og kontakte spesifikke grupper med kunder med Dynamics 365 Marketing. Hvis du vil ha mer informasjon, kan du se [Bruke segmenter fra Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Hvis du bruker de nye funksjonene i Dynamics 365 Marketing til orkestrering av kundereiser i sanntid i en Dataverse-organisasjon, trenger du ikke opprette en standardeksport til Dynamics 365 Marketing. Kontakter og segmenter fra Customer Insights er tilgjengelige direkte i Dynamics 365 Marketing etter tilkobling til Marketing og Customer Insights. Før du sletter eksisterende eksporter, ser du gjennom dokumentasjonen for [hvordan du kobler sammen Customer Insights og Dynamics 365 Marketing-kundereiseiverksetting](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Forutsetninger for en tilkobling

- Kontaktoppføringer må finnes i Dynamics 365 Marketing før du kan eksportere et segment fra Customer Insights til Marketing. Les mer om hvordan du inntar kontakter i [Dynamics 365 Marketing ved hjelp av Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Eksport av segmenter fra Customer Insights til Marketing oppretter ikke nye kontaktoppføringer i Marketing-forekomstene. Kontaktoppføringene fra Marketing må legges inn i Customer Insights og brukes som en datakilde. De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.

## <a name="set-up-connection-to-marketing"></a>Konfigurere tilkobling til Marketing

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Dynamics 365 Marketing** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Skriv inn organisasjonens URL-adresse for Marketing i **Serveradresse**-feltet.

1. I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Marketing-konto.

1. Tilordne Kontakt-ID-feltet i kundeenheten til kontakt-ID-en for Dynamics 365.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
