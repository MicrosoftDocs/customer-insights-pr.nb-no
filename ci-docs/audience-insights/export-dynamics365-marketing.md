---
title: Eksportere Customer Insights-data til Dynamics 365 Marketing
description: Lær hvordan du konfigurerer tilkoblingen til Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643785"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="ae3f0-103">Kobling for Dynamics 365 Marketing (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="ae3f0-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ae3f0-104">Bruk [segmenter](segments.md) til å generere kampanjer og kontakte spesifikke grupper med kunder med Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="ae3f0-105">Hvis du vil ha mer informasjon, kan du se [Bruke segmenter fra Dynamics 365 Customer Insights med Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="ae3f0-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="ae3f0-106">Forutsetning</span><span class="sxs-lookup"><span data-stu-id="ae3f0-106">Prerequisite</span></span>

<span data-ttu-id="ae3f0-107">Kontaktoppføringer [fra Dynamics 365 Marketing har lagt inn Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ae3f0-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="ae3f0-108">Konfigurere koblingen for Marketing</span><span class="sxs-lookup"><span data-stu-id="ae3f0-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="ae3f0-109">I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ae3f0-110">Velg **Konfigurer** under **Dynamics 365 Marketing**.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="ae3f0-111">Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ae3f0-112">Skriv inn organisasjonens URL-adresse for Marketing i **Serveradresse**-feltet.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="ae3f0-113">I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Marketing-konto.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="ae3f0-114">Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="ae3f0-115">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-115">Select **Next**.</span></span>

1. <span data-ttu-id="ae3f0-116">Velg ett eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="ae3f0-117">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="ae3f0-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ae3f0-118">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="ae3f0-118">Export the data</span></span>

<span data-ttu-id="ae3f0-119">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ae3f0-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ae3f0-120">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ae3f0-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
