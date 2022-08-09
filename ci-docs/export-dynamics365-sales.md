---
title: Eksporter segmenter til Dynamics 365 Sales (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Dynamics 365 Sales.
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
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195993"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Eksporter segmenter til Dynamics 365 Sales (forhåndsversjon)

Bruk kundedata til å opprette markedsføringslister, oppfølgingsarbeidsflyter og sende ut kampanjer med Dynamics 365 Sales.

## <a name="prerequisites"></a>Forutsetning

Kontaktoppføringer må finnes i Dynamics 365 Sales før du kan eksportere et segment fra Customer Insights til Sales. Les mer om hvordan du tar inn kontakter fra [Dynamics 365 Sales ved hjelp av Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Eksport av segmenter fra Customer Insights til Sales oppretter ikke nye kontaktoppføringer i Sales-forekomstene. Kontaktoppføringene fra Sales må legges inn i Customer Insights og brukes som en datakilde. De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.

## <a name="known-limitations"></a>Kjente begrensninger

Eksport til Dynamics 365 Sales er begrenset til 100 000 per segment, som kan ta opptil 3 timer å fullføre.

## <a name="set-up-connection-to-sales"></a>Konfigurer tilkobling til Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling** og velg **Dynamics 365 Sales**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Skriv inn organisasjonens URL-adresse for Sales i **Serveradresse**-feltet.

1. I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Sales-konto.

1. Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Dynamics 365 Sales-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg Kontakt-ID-feltet i kundeenheten som samsvarer med kontakt-ID-en for Dynamics 365.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
