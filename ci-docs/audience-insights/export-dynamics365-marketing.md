---
title: Eksportere Customer Insights-data til Dynamics 365 Marketing
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759649"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="36e4b-103">Bruke segmenter i Dynamics 365 Marketing (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="36e4b-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="36e4b-104">Bruk [segmenter](segments.md) til å generere kampanjer og kontakte spesifikke grupper med kunder med Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="36e4b-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="36e4b-105">Hvis du vil ha mer informasjon, kan du se [Bruke segmenter fra Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="36e4b-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="36e4b-106">Forutsetninger for en tilkobling</span><span class="sxs-lookup"><span data-stu-id="36e4b-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="36e4b-107">Kontaktoppføringer må finnes i Dynamics 365 Marketing før du kan eksportere et segment fra Customer Insights til Marketing.</span><span class="sxs-lookup"><span data-stu-id="36e4b-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="36e4b-108">Les mer om hvordan du inntar kontakter i [Dynamics 365 Marketing ved hjelp av Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="36e4b-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="36e4b-109">Hvis du eksporterer segmenter fra målgruppeinnsikt til Marketing, opprettes ikke nye kontaktoppføringer i Marketing-forekomstene.</span><span class="sxs-lookup"><span data-stu-id="36e4b-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="36e4b-110">Kontaktoppføringene fra Marketing må legges inn i målgruppeinnsikt og brukes som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="36e4b-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="36e4b-111">De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.</span><span class="sxs-lookup"><span data-stu-id="36e4b-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="36e4b-112">Konfigurere tilkobling til Marketing</span><span class="sxs-lookup"><span data-stu-id="36e4b-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="36e4b-113">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="36e4b-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="36e4b-114">Velg **Legg til tilkobling**, og velg **Dynamics 365 Marketing** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="36e4b-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="36e4b-115">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="36e4b-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="36e4b-116">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="36e4b-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="36e4b-117">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="36e4b-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="36e4b-118">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="36e4b-118">Choose who can use this connection.</span></span> <span data-ttu-id="36e4b-119">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="36e4b-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="36e4b-120">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="36e4b-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="36e4b-121">Skriv inn organisasjonens URL-adresse for Marketing i **Serveradresse**-feltet.</span><span class="sxs-lookup"><span data-stu-id="36e4b-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="36e4b-122">I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Marketing-konto.</span><span class="sxs-lookup"><span data-stu-id="36e4b-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="36e4b-123">Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.</span><span class="sxs-lookup"><span data-stu-id="36e4b-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="36e4b-124">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="36e4b-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="36e4b-125">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="36e4b-125">Configure an export</span></span>

<span data-ttu-id="36e4b-126">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="36e4b-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="36e4b-127">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="36e4b-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="36e4b-128">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="36e4b-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="36e4b-129">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="36e4b-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="36e4b-130">Velg en tilkobling fra Dynamics 365 Marketing-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="36e4b-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="36e4b-131">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="36e4b-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="36e4b-132">Velg ett eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="36e4b-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="36e4b-133">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="36e4b-133">Select **Save**.</span></span>

<span data-ttu-id="36e4b-134">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="36e4b-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="36e4b-135">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="36e4b-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="36e4b-136">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="36e4b-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
