---
title: Eksportere Customer Insights-data til Dynamics 365 Marketing
description: Lær hvordan du konfigurerer tilkoblingen til Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597615"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Kobling for Dynamics 365 Marketing (forhåndsvisning)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Bruk [segmenter](segments.md) til å generere kampanjer og kontakte spesifikke grupper med kunder med Dynamics 365 Marketing. Hvis du vil ha mer informasjon, kan du se [Bruke segmenter fra Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Forutsetning

- Kontaktoppføringer må finnes i Dynamics 365 Marketing før du kan eksportere et segment fra Customer Insights til Marketing. Les mer om hvordan du inntar kontakter i [Dynamics 365 Marketing ved hjelp av Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Hvis du eksporterer segmenter fra målgruppeinnsikt til Marketing, opprettes ikke nye kontaktoppføringer i Marketing-forekomstene. Kontaktoppføringene fra Marketing må legges inn i målgruppeinnsikt og brukes som en datakilde. De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.

## <a name="configure-the-connector-for-marketing"></a>Konfigurere koblingen for Marketing

1. I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.

1. Velg **Konfigurer** under **Dynamics 365 Marketing**.

1. Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.

1. Skriv inn organisasjonens URL-adresse for Marketing i **Serveradresse**-feltet.

1. I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Marketing-konto.

1. Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.

1. Velg **Neste**.

1. Velg ett eller flere segmenter.

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]