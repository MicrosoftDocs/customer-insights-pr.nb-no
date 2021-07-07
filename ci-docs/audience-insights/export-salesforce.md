---
title: Eksportere Customer Insights-data til Salesforce Marketing Cloud
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314651"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="0d50d-103">Eksportere segmenter og andre data til Salesforce Marketing Cloud (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="0d50d-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="0d50d-104">Bruk kundedataene i Salesforce Marketing Cloud ved å eksportere dem via en SFTP-plassering (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="0d50d-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0d50d-105">Forutsetninger for tilkobling</span><span class="sxs-lookup"><span data-stu-id="0d50d-105">Prerequisites for connection</span></span>

- <span data-ttu-id="0d50d-106">Tilgjengelighet av SFTP-vert og tilsvarende administratorlegitimasjon.</span><span class="sxs-lookup"><span data-stu-id="0d50d-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="0d50d-107">Konfigurere SFTP-steder for Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="0d50d-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="0d50d-108">Kjente begrensninger</span><span class="sxs-lookup"><span data-stu-id="0d50d-108">Known limitations</span></span>

- <span data-ttu-id="0d50d-109">Kjøretiden for en eksport avhenger av systemytelsen.</span><span class="sxs-lookup"><span data-stu-id="0d50d-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="0d50d-110">Vi anbefaler to CPU-kjerner og 1 GB minne som minimal konfigurasjon av serveren.</span><span class="sxs-lookup"><span data-stu-id="0d50d-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="0d50d-111">Det kan ta 90 minutter å eksportere enheter med opptil 100 millioner kundeprofiler når anbefalt minimumskonfigurasjon brukes.</span><span class="sxs-lookup"><span data-stu-id="0d50d-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="0d50d-112">Konfigurere tilkoblingen til Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="0d50d-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="0d50d-113">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="0d50d-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0d50d-114">Velg **Legg til tilkobling**, og velg **Salesforce Marketing Cloud** for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0d50d-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="0d50d-115">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="0d50d-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0d50d-116">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0d50d-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0d50d-117">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0d50d-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0d50d-118">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0d50d-118">Choose who can use this connection.</span></span> <span data-ttu-id="0d50d-119">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="0d50d-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0d50d-120">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0d50d-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0d50d-121">Angi et **brukernavn**, et **passord** og et **vertsnavn** og **eksportmappe** for SFTP-kontoen.</span><span class="sxs-lookup"><span data-stu-id="0d50d-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="0d50d-122">Velg **Bekreft** for å teste tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0d50d-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="0d50d-123">Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.</span><span class="sxs-lookup"><span data-stu-id="0d50d-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0d50d-124">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="0d50d-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0d50d-125">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="0d50d-125">Configure an export</span></span>

<span data-ttu-id="0d50d-126">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="0d50d-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0d50d-127">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0d50d-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0d50d-128">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="0d50d-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0d50d-129">Velg **Legg til mål** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="0d50d-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0d50d-130">Velg en tilkobling fra SFTP-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="0d50d-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="0d50d-131">Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="0d50d-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0d50d-132">Velg om du vil eksportere dataene **Komprimert** eller **Pakket ut** og **feltskilletegnet** for de eksporterte filene.</span><span class="sxs-lookup"><span data-stu-id="0d50d-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="0d50d-133">Velg enhetene du vil eksportere, for eksempel segmenter.</span><span class="sxs-lookup"><span data-stu-id="0d50d-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0d50d-134">Hver valgte enhet blir delt opp i opptil fem utdatafiler når de eksporteres.</span><span class="sxs-lookup"><span data-stu-id="0d50d-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="0d50d-135">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="0d50d-135">Select **Save**.</span></span>

<span data-ttu-id="0d50d-136">Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.</span><span class="sxs-lookup"><span data-stu-id="0d50d-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0d50d-137">Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0d50d-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0d50d-138">Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0d50d-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="0d50d-139">Importere Customer Insights-data fra SFTP-sted til Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="0d50d-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="0d50d-140">Opprett [datautvidelser i Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) for å importere Customer Insights-datafilen fra SFTP-plasseringen.</span><span class="sxs-lookup"><span data-stu-id="0d50d-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="0d50d-141">[Importer dataene fra SFTP-plasseringen](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) til datautvidelsen for Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="0d50d-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="0d50d-142">Konfigurer automatiseringen til å importere dataene til datautvidelsene.</span><span class="sxs-lookup"><span data-stu-id="0d50d-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="0d50d-143">Lær mer om [fildroppingsautomatiseringer og planlagte automatiseringer](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="0d50d-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="0d50d-144">Definere [fildroppingsautomatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) eller en [planlagt automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="0d50d-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="0d50d-145">Her er et eksempel på [automatisering med SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="0d50d-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0d50d-146">Datapersonvern og -samsvar</span><span class="sxs-lookup"><span data-stu-id="0d50d-146">Data privacy and compliance</span></span>

<span data-ttu-id="0d50d-147">Når du aktiverer Dynamics 365 Customer Insights for overføring av data via SFTP, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data.</span><span class="sxs-lookup"><span data-stu-id="0d50d-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0d50d-148">Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at eksportmålet oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha.</span><span class="sxs-lookup"><span data-stu-id="0d50d-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0d50d-149">Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0d50d-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0d50d-150">Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.</span><span class="sxs-lookup"><span data-stu-id="0d50d-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
