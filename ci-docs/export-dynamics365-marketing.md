---
title: Eksporter segmenter til Dynamics 365 Marketing (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196636"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Eksporter segmenter til Dynamics 365 Marketing (forhåndsversjon)

Bruk [segmenter](segments.md) til å generere kampanjer og kontakte spesifikke grupper med kunder med [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Hvis du bruker de nye funksjonene i Dynamics 365 Marketing til orkestrering av kundereiser i sanntid i en Dataverse-organisasjon, trenger du ikke opprette en standardeksport til Dynamics 365 Marketing. Kontakter og segmenter fra Customer Insights er tilgjengelige direkte i Dynamics 365 Marketing etter tilkobling til Marketing og Customer Insights. Før du sletter eksisterende eksporter, ser du gjennom dokumentasjonen for [hvordan du kobler sammen Customer Insights og Dynamics 365 Marketing-kundereiseiverksetting](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Forutsetning

Kontaktoppføringer må finnes i Dynamics 365 Marketing før du kan eksportere et segment fra Customer Insights til Marketing. Les mer om hvordan du inntar kontakter i [Dynamics 365 Marketing ved hjelp av Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Eksport av segmenter fra Customer Insights til Marketing oppretter ikke nye kontaktoppføringer i Marketing-forekomstene. Kontaktoppføringene fra Marketing må legges inn i Customer Insights og brukes som en datakilde. De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.

## <a name="set-up-connection-to-marketing"></a>Konfigurere tilkobling til Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling** og velg **Dynamics 365 Marketing**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Skriv inn organisasjonens URL-adresse for Marketing i **Serveradresse**-feltet.

1. I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Marketing-konto.

1. Tilordne Kontakt-ID-feltet i kundeenheten til kontakt-ID-en for Dynamics 365.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Dynamics 365 Marketing-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg Kontakt-ID-feltet i kundeenheten som samsvarer med kontakt-ID-en for Dynamics 365.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
