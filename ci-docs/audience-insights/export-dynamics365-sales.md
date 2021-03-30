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
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="405d1-103">Kobling for Dynamics 365 Sales (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="405d1-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="405d1-104">Bruk kundedata til å opprette markedsføringslister, oppfølgingsarbeidsflyter og sende ut kampanjer med Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="405d1-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="405d1-105">Forutsetning</span><span class="sxs-lookup"><span data-stu-id="405d1-105">Prerequisite</span></span>

1. <span data-ttu-id="405d1-106">Kontaktoppføringer må finnes i Dynamics 365 Sales før du kan eksportere et segment fra Customer Insights til Sales.</span><span class="sxs-lookup"><span data-stu-id="405d1-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="405d1-107">Les mer om hvordan du inntar kontakter i [Dynamics 365 Sales ved hjelp av Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="405d1-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="405d1-108">Hvis du eksporterer segmenter fra målgruppeinnsikt til Sales, opprettes ikke nye kontaktoppføringer i Sales-forekomstene.</span><span class="sxs-lookup"><span data-stu-id="405d1-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="405d1-109">Kontaktoppføringene fra Sales må legges inn i målgruppeinnsikt og brukes som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="405d1-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="405d1-110">De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.</span><span class="sxs-lookup"><span data-stu-id="405d1-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="405d1-111">Konfigurere koblingen for Sales</span><span class="sxs-lookup"><span data-stu-id="405d1-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="405d1-112">I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="405d1-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="405d1-113">Velg **Konfigurer** under **Dynamics 365 Sales**.</span><span class="sxs-lookup"><span data-stu-id="405d1-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="405d1-114">Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="405d1-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="405d1-115">Skriv inn organisasjonens URL-adresse for Sales i **Serveradresse**-feltet.</span><span class="sxs-lookup"><span data-stu-id="405d1-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="405d1-116">I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Sales-konto.</span><span class="sxs-lookup"><span data-stu-id="405d1-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="405d1-117">Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.</span><span class="sxs-lookup"><span data-stu-id="405d1-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="405d1-118">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="405d1-118">Select **Next**.</span></span>

1. <span data-ttu-id="405d1-119">Velg ett eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="405d1-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="405d1-120">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="405d1-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="405d1-121">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="405d1-121">Export the data</span></span>

<span data-ttu-id="405d1-122">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="405d1-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="405d1-123">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="405d1-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]