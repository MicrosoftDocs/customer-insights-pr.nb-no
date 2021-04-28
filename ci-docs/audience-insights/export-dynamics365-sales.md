---
title: Eksportere Customer Insights-data til Dynamics 365 Sales
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759616"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="6257d-103">Bruke segmenter i Dynamics 365 Sales (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="6257d-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6257d-104">Bruk kundedata til å opprette markedsføringslister, oppfølgingsarbeidsflyter og sende ut kampanjer med Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="6257d-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="6257d-105">Forutsetninger for en tilkobling</span><span class="sxs-lookup"><span data-stu-id="6257d-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="6257d-106">Kontaktoppføringer må finnes i Dynamics 365 Sales før du kan eksportere et segment fra Customer Insights til Sales.</span><span class="sxs-lookup"><span data-stu-id="6257d-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="6257d-107">Les mer om hvordan du inntar kontakter i [Dynamics 365 Sales ved hjelp av Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="6257d-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="6257d-108">Hvis du eksporterer segmenter fra målgruppeinnsikt til Sales, opprettes ikke nye kontaktoppføringer i Sales-forekomstene.</span><span class="sxs-lookup"><span data-stu-id="6257d-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="6257d-109">Kontaktoppføringene fra Sales må legges inn i målgruppeinnsikt og brukes som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="6257d-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="6257d-110">De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.</span><span class="sxs-lookup"><span data-stu-id="6257d-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="6257d-111">Konfigurer tilkoblingen til Sales</span><span class="sxs-lookup"><span data-stu-id="6257d-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="6257d-112">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="6257d-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6257d-113">Velg **Legg til tilkobling**, og velg **Dynamics 365 Sales** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="6257d-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="6257d-114">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="6257d-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6257d-115">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="6257d-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6257d-116">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="6257d-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6257d-117">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="6257d-117">Choose who can use this connection.</span></span> <span data-ttu-id="6257d-118">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="6257d-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6257d-119">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6257d-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6257d-120">Skriv inn organisasjonens URL-adresse for Sales i **Serveradresse**-feltet.</span><span class="sxs-lookup"><span data-stu-id="6257d-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="6257d-121">I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Sales-konto.</span><span class="sxs-lookup"><span data-stu-id="6257d-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="6257d-122">Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.</span><span class="sxs-lookup"><span data-stu-id="6257d-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="6257d-123">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="6257d-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="6257d-124">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="6257d-124">Configure an export</span></span>

<span data-ttu-id="6257d-125">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="6257d-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6257d-126">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6257d-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6257d-127">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="6257d-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6257d-128">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="6257d-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6257d-129">Velg en tilkobling fra Dynamics 365 Sales-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="6257d-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="6257d-130">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="6257d-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6257d-131">Velg ett eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="6257d-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="6257d-132">Velg **Lagre**</span><span class="sxs-lookup"><span data-stu-id="6257d-132">Select **Save**</span></span>

<span data-ttu-id="6257d-133">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="6257d-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6257d-134">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6257d-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6257d-135">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6257d-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
