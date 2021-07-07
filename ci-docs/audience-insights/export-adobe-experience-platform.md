---
title: Eksporter Customer Insights-data til Adobe Experience Platform
description: Lær hvordan du bruker målgruppeinnsiktssegmenter på Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305536"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="a51b2-103">Bruk Customer Insights-segmenter i Adobe Experience Platform (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="a51b2-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="a51b2-104">Som bruker av målgruppeinnsikt i Dynamics 365 Customer Insights har du kanskje opprettet segmenter for å gjøre markedsføringskampanjene mer effektive ved å rette deg mot relevante målgrupper.</span><span class="sxs-lookup"><span data-stu-id="a51b2-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="a51b2-105">Hvis du vil bruke et segment fra målgruppeinnsikt i Adobe Experience Platform og programmer som Adobe Campaign Standard, må du følge noen få trinn som er beskrevet i denne artikkelen.</span><span class="sxs-lookup"><span data-stu-id="a51b2-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Prosessdiagram for trinnene beskrevet i denne artikkelen.":::

## <a name="prerequisites"></a><span data-ttu-id="a51b2-107">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="a51b2-107">Prerequisites</span></span>

-   <span data-ttu-id="a51b2-108">Dynamics 365 Customer Insights-lisens</span><span class="sxs-lookup"><span data-stu-id="a51b2-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="a51b2-109">Adobe Experience Platform-lisens</span><span class="sxs-lookup"><span data-stu-id="a51b2-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="a51b2-110">Adobe Campaign Standard-lisens</span><span class="sxs-lookup"><span data-stu-id="a51b2-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="a51b2-111">Azure Blob Storage-konto</span><span class="sxs-lookup"><span data-stu-id="a51b2-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="a51b2-112">Kampanjeoversikt</span><span class="sxs-lookup"><span data-stu-id="a51b2-112">Campaign Overview</span></span>

<span data-ttu-id="a51b2-113">For en bedre forståelse av hvordan du kan bruke segmenter fra målgruppeinnsikt i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampanje.</span><span class="sxs-lookup"><span data-stu-id="a51b2-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="a51b2-114">La oss anta at firmaet ditt tilbyr en månedlig abonnementsbasert tjeneste til kundene i USA.</span><span class="sxs-lookup"><span data-stu-id="a51b2-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="a51b2-115">Du ønsker å identifisere kunder som har abonnementer som skal fornyes i løpet av de neste åtte dagene, men som ennå ikke har fornyet abonnementet.</span><span class="sxs-lookup"><span data-stu-id="a51b2-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="a51b2-116">Hvis du vil beholde disse kundene, må du sende dem et kampanjetilbud via e-post ved hjelp av Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="a51b2-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="a51b2-117">I dette eksemplet skal vi kjøre den promoterende e-postkampanjen én gang.</span><span class="sxs-lookup"><span data-stu-id="a51b2-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="a51b2-118">Denne artikkelen dekker ikke brukstilfellet for kjøring av kampanjen flere ganger.</span><span class="sxs-lookup"><span data-stu-id="a51b2-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="a51b2-119">Identifiser målgruppen</span><span class="sxs-lookup"><span data-stu-id="a51b2-119">Identify your target audience</span></span>

<span data-ttu-id="a51b2-120">I vårt scenario antar vi at e-postadressene til kundene er tilgjengelige i målgruppeinnsikt, og at kampanjepreferansene deres ble analysert for å identifisere medlemmer i segmentet.</span><span class="sxs-lookup"><span data-stu-id="a51b2-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="a51b2-121">[Segmentet du definerte i målgruppeinnsikt](segments.md), kalles **ChurnProneCustomers**, og du planlegger å sende e-postkampanjen til disse kundene.</span><span class="sxs-lookup"><span data-stu-id="a51b2-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skjermbilde av segmentsiden med ChurnProneCustomers -segmentet opprettet.":::

<span data-ttu-id="a51b2-123">E-postmeldingen for tilbudet du vil sende ut, inneholder kundens fornavn, etternavn og sluttdatoen for abonnementet.</span><span class="sxs-lookup"><span data-stu-id="a51b2-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="a51b2-124">Den informerer kundene om rabatten de får hvis de fornyer abonnementet før abonnementet avsluttes.</span><span class="sxs-lookup"><span data-stu-id="a51b2-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="a51b2-125">Eksporter målgruppen</span><span class="sxs-lookup"><span data-stu-id="a51b2-125">Export your target audience</span></span>

<span data-ttu-id="a51b2-126">Når målgruppen er identifisert, kan vi konfigurere eksporten fra målgruppeinnsikt til en Azure Blob Storage-konto.</span><span class="sxs-lookup"><span data-stu-id="a51b2-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="a51b2-127">Konfigurer en tilkobling</span><span class="sxs-lookup"><span data-stu-id="a51b2-127">Configure a connection</span></span>

1. <span data-ttu-id="a51b2-128">Gå til **Administrator** > **Tilkoblinger**.</span><span class="sxs-lookup"><span data-stu-id="a51b2-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a51b2-129">Velg **Legg til tilkobling**, og velg **Azure Blob-lagring**, eller velg **Konfigurer** på **Azure Blob-lagring**-flisen for å konfigurere tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="a51b2-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurasjon-flis for Azure Blob Storage."::: 

1. <span data-ttu-id="a51b2-131">Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.</span><span class="sxs-lookup"><span data-stu-id="a51b2-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a51b2-132">Navnet og tilkoblingstypen beskriver denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="a51b2-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a51b2-133">Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="a51b2-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a51b2-134">Velg hvem som kan bruke denne tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="a51b2-134">Choose who can use this connection.</span></span> <span data-ttu-id="a51b2-135">Hvis du ikke gjør noe, vil standarden være Administratorer.</span><span class="sxs-lookup"><span data-stu-id="a51b2-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a51b2-136">Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a51b2-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a51b2-137">Angi **Kontonavn:**, **Kontonøkkel** og **Beholder** for Blob Storage-kontoen du vil eksportere segmentet til.</span><span class="sxs-lookup"><span data-stu-id="a51b2-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skjermbilde av konfigurasjonen av lagringskontoen. "::: 
   
    - <span data-ttu-id="a51b2-139">Hvis du vil finne ut mer om hvordan du finner navn på forretningsforbindelse og kontonøkkel for Blob Storage, kan du se [Behandle innstillinger for lagringskonto i Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="a51b2-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="a51b2-140">Hvis du vil lære hvordan du oppretter en beholder, kan du se [Opprette en beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="a51b2-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="a51b2-141">Velg **Lagre** for å fullføre tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="a51b2-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="a51b2-142">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="a51b2-142">Configure an export</span></span>

<span data-ttu-id="a51b2-143">Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen.</span><span class="sxs-lookup"><span data-stu-id="a51b2-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a51b2-144">Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a51b2-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a51b2-145">Gå til **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="a51b2-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a51b2-146">Velg **Legg til eksport** for å opprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="a51b2-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="a51b2-147">Velg en tilkobling fra Azure Blob Storage-delen i feltet **Tilkobling for eksport**.</span><span class="sxs-lookup"><span data-stu-id="a51b2-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="a51b2-148">Hvis navnet på denne delen ikke vises, er ingen tilkoblinger av denne typen tilgjengelige for deg.</span><span class="sxs-lookup"><span data-stu-id="a51b2-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="a51b2-149">Velg segmentet du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="a51b2-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="a51b2-150">I dette eksemplet er det **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a51b2-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skjermbilde av brukergrensesnittet for segmentvalg med ChurnProneCustomers-segmentet valgt.":::

1. <span data-ttu-id="a51b2-152">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="a51b2-152">Select **Save**.</span></span>

<span data-ttu-id="a51b2-153">Når du har lagret eksportmålet, finner du det i **Data** > **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="a51b2-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="a51b2-154">Du kan nå [eksportere segmentet ved behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a51b2-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="a51b2-155">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md).</span><span class="sxs-lookup"><span data-stu-id="a51b2-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a51b2-156">Kontroller at antall oppføringer i det eksporterte segmentet er innenfor den tillatte grensen for Adobe Campaign Standard-lisensen.</span><span class="sxs-lookup"><span data-stu-id="a51b2-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="a51b2-157">Eksporterte data lagres i Azure Blob Storage-beholderen du konfigurerte ovenfor.</span><span class="sxs-lookup"><span data-stu-id="a51b2-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="a51b2-158">Følgende mappebane opprettes automatisk i beholderen:</span><span class="sxs-lookup"><span data-stu-id="a51b2-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="a51b2-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="a51b2-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="a51b2-160">Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="a51b2-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="a51b2-161">*model.json* for de eksporterte enhetene er på *%ExportDestinationName%*-nivået.</span><span class="sxs-lookup"><span data-stu-id="a51b2-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="a51b2-162">Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="a51b2-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="a51b2-163">Definer Experience Data Model (XDM) i Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="a51b2-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="a51b2-164">Før de eksporterte dataene fra målgruppeinnsikt kan brukes i Adobe Experience Platform, må vi definere Experience Data Model-skjemaet og [konfigurere dataene for kundeprofilen i sanntid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="a51b2-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="a51b2-165">Finn ut [hva XDM er](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) og forstå det [grunnleggende innen skjemakomposisjon](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="a51b2-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="a51b2-166">Importer data til Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="a51b2-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="a51b2-167">Nå som alt er klart, må vi importere de klargjorte målgruppedataene fra målgruppeinnsikt til Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="a51b2-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="a51b2-168">Først må du [opprette en Azure Blob Storage-kildetilkobling](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="a51b2-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="a51b2-169">Når du har definert kildetilkoblingen, må du [konfigurere en dataflyt](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for en skylagringstilkobling for å importere segmentutdataene fra målgruppeinnsikt til Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="a51b2-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="a51b2-170">Opprett en målgruppe i Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="a51b2-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="a51b2-171">Hvis du vil sende e-posten for denne kampanjen, bruker vi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="a51b2-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="a51b2-172">Når du har importert dataene til Adobe Experience Platform, må vi [opprette en målgruppe](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard ved å bruke dataene i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="a51b2-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="a51b2-173">Lær hvordan du [bruker segmentverktøyet](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) i Adobe Campaign Standard til å definere en målgruppe basert på dataene i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="a51b2-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="a51b2-174">Opprett og send e-posten ved hjelp av Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="a51b2-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="a51b2-175">Opprett e-postinnholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-posten din.</span><span class="sxs-lookup"><span data-stu-id="a51b2-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på e-post med fornyelsestilbud fra Adobe Campaign Standard.":::
