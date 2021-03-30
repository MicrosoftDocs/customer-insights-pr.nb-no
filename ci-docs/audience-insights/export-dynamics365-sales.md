---
title: Eksportere Customer Insights-data til Dynamics 365 Sales
description: Lær hvordan du konfigurerer tilkoblingen til Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598121"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Kobling for Dynamics 365 Sales (forhåndsvisning)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Bruk kundedata til å opprette markedsføringslister, oppfølgingsarbeidsflyter og sende ut kampanjer med Dynamics 365 Sales.

## <a name="prerequisite"></a>Forutsetning

1. Kontaktoppføringer må finnes i Dynamics 365 Sales før du kan eksportere et segment fra Customer Insights til Sales. Les mer om hvordan du inntar kontakter i [Dynamics 365 Sales ved hjelp av Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Hvis du eksporterer segmenter fra målgruppeinnsikt til Sales, opprettes ikke nye kontaktoppføringer i Sales-forekomstene. Kontaktoppføringene fra Sales må legges inn i målgruppeinnsikt og brukes som en datakilde. De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.

## <a name="configure-the-connector-for-sales"></a>Konfigurere koblingen for Sales

1. I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.

1. Velg **Konfigurer** under **Dynamics 365 Sales**.

1. Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.

1. Skriv inn organisasjonens URL-adresse for Sales i **Serveradresse**-feltet.

1. I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Sales-konto.

1. Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.

1. Velg **Neste**.

1. Velg ett eller flere segmenter.

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]