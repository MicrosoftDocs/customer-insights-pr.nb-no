---
title: Eksportere Customer Insights-data til Dynamics 365 Sales
description: Lær hvordan du konfigurerer tilkoblingen til Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643830"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="467a8-103">Kobling for Dynamics 365 Sales (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="467a8-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="467a8-104">Bruk kundedata til å opprette markedsføringslister, oppfølgingsarbeidsflyter og sende ut kampanjer med Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="467a8-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="467a8-105">Forutsetning</span><span class="sxs-lookup"><span data-stu-id="467a8-105">Prerequisite</span></span>

<span data-ttu-id="467a8-106">Kontaktoppføringer [fra Dynamics 365 Sales som er lagt inn ved hjelp av Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="467a8-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="467a8-107">Konfigurere koblingen for Sales</span><span class="sxs-lookup"><span data-stu-id="467a8-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="467a8-108">I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="467a8-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="467a8-109">Velg **Konfigurer** under **Dynamics 365 Sales**.</span><span class="sxs-lookup"><span data-stu-id="467a8-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="467a8-110">Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="467a8-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="467a8-111">Skriv inn organisasjonens URL-adresse for Sales i **Serveradresse**-feltet.</span><span class="sxs-lookup"><span data-stu-id="467a8-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="467a8-112">I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Sales-konto.</span><span class="sxs-lookup"><span data-stu-id="467a8-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="467a8-113">Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.</span><span class="sxs-lookup"><span data-stu-id="467a8-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="467a8-114">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="467a8-114">Select **Next**.</span></span>

1. <span data-ttu-id="467a8-115">Velg ett eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="467a8-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="467a8-116">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="467a8-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="467a8-117">Eksportere dataene</span><span class="sxs-lookup"><span data-stu-id="467a8-117">Export the data</span></span>

<span data-ttu-id="467a8-118">Du kan [eksportere data etter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="467a8-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="467a8-119">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="467a8-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
