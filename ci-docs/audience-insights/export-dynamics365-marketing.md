---
title: Eksportere Customer Insights-data til Dynamics 365 Marketing
description: Lær hvordan du konfigurerer tilkoblingen til Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269066"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="4fcaa-103">Kobling for Dynamics 365 Marketing (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="4fcaa-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4fcaa-104">Bruk [segmenter](segments.md) til å generere kampanjer og kontakte spesifikke grupper med kunder med Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="4fcaa-105">Hvis du vil ha mer informasjon, kan du se [Bruke segmenter fra Dynamics 365 Customer Insights med Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="4fcaa-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="4fcaa-106">Forutsetning</span><span class="sxs-lookup"><span data-stu-id="4fcaa-106">Prerequisite</span></span>

- <span data-ttu-id="4fcaa-107">Kontaktoppføringer må finnes i Dynamics 365 Marketing før du kan eksportere et segment fra Customer Insights til Marketing.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="4fcaa-108">Les mer om hvordan du inntar kontakter i [Dynamics 365 Marketing ved hjelp av Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="4fcaa-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="4fcaa-109">Hvis du eksporterer segmenter fra målgruppeinnsikt til Marketing, opprettes ikke nye kontaktoppføringer i Marketing-forekomstene.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="4fcaa-110">Kontaktoppføringene fra Marketing må legges inn i målgruppeinnsikt og brukes som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="4fcaa-111">De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="4fcaa-112">Konfigurere koblingen for Marketing</span><span class="sxs-lookup"><span data-stu-id="4fcaa-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="4fcaa-113">I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4fcaa-114">Velg **Konfigurer** under **Dynamics 365 Marketing**.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="4fcaa-115">Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4fcaa-116">Skriv inn organisasjonens URL-adresse for Marketing i **Serveradresse**-feltet.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="4fcaa-117">I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Marketing-konto.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="4fcaa-118">Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="4fcaa-119">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-119">Select **Next**.</span></span>

1. <span data-ttu-id="4fcaa-120">Velg ett eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="4fcaa-121">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="4fcaa-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4fcaa-122">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="4fcaa-122">Export the data</span></span>

<span data-ttu-id="4fcaa-123">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4fcaa-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="4fcaa-124">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4fcaa-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]