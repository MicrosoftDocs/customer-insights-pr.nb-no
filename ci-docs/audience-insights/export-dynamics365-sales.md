---
title: Eksportere Customer Insights-data til Dynamics 365 Sales
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976238"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="9a389-103">Bruke segmenter i Dynamics 365 Sales (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="9a389-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9a389-104">Bruk kundedata til å opprette markedsføringslister, oppfølgingsarbeidsflyter og sende ut kampanjer med Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9a389-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="9a389-105">Forutsetninger for en tilkobling</span><span class="sxs-lookup"><span data-stu-id="9a389-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="9a389-106">Kontaktoppføringer må finnes i Dynamics 365 Sales før du kan eksportere et segment fra Customer Insights til Sales.</span><span class="sxs-lookup"><span data-stu-id="9a389-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="9a389-107">Les mer om hvordan du inntar kontakter i [Dynamics 365 Sales ved hjelp av Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9a389-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="9a389-108">Hvis du eksporterer segmenter fra målgruppeinnsikt til Sales, opprettes ikke nye kontaktoppføringer i Sales-forekomstene.</span><span class="sxs-lookup"><span data-stu-id="9a389-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="9a389-109">Kontaktoppføringene fra Sales må legges inn i målgruppeinnsikt og brukes som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="9a389-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="9a389-110">De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.</span><span class="sxs-lookup"><span data-stu-id="9a389-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="9a389-111">Konfigurer tilkoblingen til Sales</span><span class="sxs-lookup"><span data-stu-id="9a389-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="9a389-112">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="9a389-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9a389-113">Velg **Legg til tilkobling**, og velg **Dynamics 365 Sales** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="9a389-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="9a389-114">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="9a389-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9a389-115">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="9a389-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9a389-116">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="9a389-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9a389-117">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="9a389-117">Choose who can use this connection.</span></span> <span data-ttu-id="9a389-118">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="9a389-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9a389-119">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9a389-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9a389-120">Skriv inn organisasjonens URL-adresse for Sales i **Serveradresse**-feltet.</span><span class="sxs-lookup"><span data-stu-id="9a389-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="9a389-121">I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Sales-konto.</span><span class="sxs-lookup"><span data-stu-id="9a389-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="9a389-122">Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.</span><span class="sxs-lookup"><span data-stu-id="9a389-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="9a389-123">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="9a389-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="9a389-124">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="9a389-124">Configure an export</span></span>

<span data-ttu-id="9a389-125">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="9a389-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9a389-126">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9a389-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9a389-127">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="9a389-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9a389-128">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="9a389-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9a389-129">Velg en tilkobling fra Dynamics 365 Sales-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="9a389-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="9a389-130">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="9a389-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9a389-131">Velg ett eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="9a389-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="9a389-132">Velg **Lagre**</span><span class="sxs-lookup"><span data-stu-id="9a389-132">Select **Save**</span></span>

<span data-ttu-id="9a389-133">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="9a389-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9a389-134">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9a389-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9a389-135">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9a389-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
