---
title: Eksporter Customer Insights-data til Adobe Experience Platform
description: Lær hvordan du bruker målgruppeinnsiktssegmenter i Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596281"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="e537f-103">Bruk Customer Insights-segmenter i Adobe Experience Platform (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="e537f-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="e537f-104">Som bruker av målgruppeinnsikt for Dynamics 365 Customer Insights har du kanskje opprettet segmenter for å gjøre markedsføringskampanjene mer effektive ved å rette deg mot relevante målgrupper.</span><span class="sxs-lookup"><span data-stu-id="e537f-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="e537f-105">Hvis du vil bruke et segment fra målgruppeinnsikt i Adobe Experience Platform og programmer som Adobe Campaign Standard, må du følge noen få trinn som er beskrevet i denne artikkelen.</span><span class="sxs-lookup"><span data-stu-id="e537f-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Prosessdiagram for trinnene beskrevet i denne artikkelen.":::

## <a name="prerequisites"></a><span data-ttu-id="e537f-107">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="e537f-107">Prerequisites</span></span>

-   <span data-ttu-id="e537f-108">Dynamics 365 Customer Insights-lisens</span><span class="sxs-lookup"><span data-stu-id="e537f-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="e537f-109">Adobe Experience Platform-lisens</span><span class="sxs-lookup"><span data-stu-id="e537f-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="e537f-110">Adobe Campaign Standard-lisens</span><span class="sxs-lookup"><span data-stu-id="e537f-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="e537f-111">Azure Blob Storage-konto</span><span class="sxs-lookup"><span data-stu-id="e537f-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="e537f-112">Kampanjeoversikt</span><span class="sxs-lookup"><span data-stu-id="e537f-112">Campaign Overview</span></span>

<span data-ttu-id="e537f-113">For en bedre forståelse av hvordan du kan bruke segmenter fra målgruppeinnsikt i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampanje.</span><span class="sxs-lookup"><span data-stu-id="e537f-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="e537f-114">La oss anta at firmaet ditt tilbyr en månedlig abonnementsbasert tjeneste til kundene i USA.</span><span class="sxs-lookup"><span data-stu-id="e537f-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="e537f-115">Du ønsker å identifisere kunder som har abonnementer som skal fornyes i løpet av de neste åtte dagene, men som ennå ikke har fornyet abonnementet.</span><span class="sxs-lookup"><span data-stu-id="e537f-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="e537f-116">Hvis du vil beholde disse kundene, må du sende dem et kampanjetilbud via e-post ved hjelp av Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e537f-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="e537f-117">I dette eksemplet skal vi kjøre den promoterende e-postkampanjen én gang.</span><span class="sxs-lookup"><span data-stu-id="e537f-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="e537f-118">Denne artikkelen dekker ikke brukstilfellet for kjøring av kampanjen flere ganger.</span><span class="sxs-lookup"><span data-stu-id="e537f-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="e537f-119">Identifiser målgruppen</span><span class="sxs-lookup"><span data-stu-id="e537f-119">Identify your target audience</span></span>

<span data-ttu-id="e537f-120">I vårt scenario antar vi at e-postadressene til kundene er tilgjengelige i målgruppeinnsikt, og at kampanjepreferansene deres ble analysert for å identifisere medlemmer i segmentet.</span><span class="sxs-lookup"><span data-stu-id="e537f-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="e537f-121">[Segmentet du definerte i målgruppeinnsikt](segments.md), kalles **ChurnProneCustomers**, og du planlegger å sende e-postkampanjen til disse kundene.</span><span class="sxs-lookup"><span data-stu-id="e537f-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skjermbilde av segmentsiden med ChurnProneCustomers -segmentet opprettet.":::

<span data-ttu-id="e537f-123">E-postmeldingen for tilbudet du vil sende ut, inneholder kundens fornavn, etternavn og sluttdatoen for abonnementet.</span><span class="sxs-lookup"><span data-stu-id="e537f-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="e537f-124">Den informerer kundene om rabatten de får hvis de fornyer abonnementet før abonnementet avsluttes.</span><span class="sxs-lookup"><span data-stu-id="e537f-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="e537f-125">Eksporter målgruppen</span><span class="sxs-lookup"><span data-stu-id="e537f-125">Export your target audience</span></span>

<span data-ttu-id="e537f-126">Når målgruppen er identifisert, kan vi konfigurere eksporten fra målgruppeinnsikt til en Azure Blob Storage-konto.</span><span class="sxs-lookup"><span data-stu-id="e537f-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="e537f-127">I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="e537f-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e537f-128">På flisen **Azure Blob Storage** velger du **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="e537f-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurasjon-flis for Azure Blob Storage.":::

1. <span data-ttu-id="e537f-130">Angi et **visningsnavn** for dette nye eksportmålet, og angi deretter **kontonavnet**, **kontonøkkelen** og **beholderen** for Azure Blob Storage-kontoen du vil eksportere segmentet til.</span><span class="sxs-lookup"><span data-stu-id="e537f-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skjermbilde av konfigurasjonen av lagringskontoen. "::: 

   - <span data-ttu-id="e537f-132">Hvis du vil vite mer om hvordan du finner navnet og nøkkelen til Azure Blob Storage-kontoen, kan du se [Administrere lagringskontoinnstillinger i Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e537f-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="e537f-133">Hvis du vil lære hvordan du oppretter en beholder, kan du se [Opprette en beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="e537f-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="e537f-134">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="e537f-134">Select **Next**.</span></span>

1. <span data-ttu-id="e537f-135">Velg segmentet du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="e537f-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="e537f-136">I dette eksemplet er det **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="e537f-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skjermbilde av brukergrensesnittet for segmentvalg med ChurnProneCustomers-segmentet valgt.":::

1. <span data-ttu-id="e537f-138">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="e537f-138">Select **Save**.</span></span>

<span data-ttu-id="e537f-139">Når du har lagret eksportmålet, finner du det i **Administrator** > **Eksporter** > **Mine eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="e537f-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Skjermbilde med listen over eksporter og eksempelsegment uthevet.":::

<span data-ttu-id="e537f-141">Du kan nå [eksportere segmentet ved behov](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e537f-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="e537f-142">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md).</span><span class="sxs-lookup"><span data-stu-id="e537f-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e537f-143">Kontroller at antall oppføringer i det eksporterte segmentet er innenfor den tillatte grensen for Adobe Campaign Standard-lisensen.</span><span class="sxs-lookup"><span data-stu-id="e537f-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="e537f-144">Eksporterte data lagres i Azure Blob Storage-beholderen du konfigurerte ovenfor.</span><span class="sxs-lookup"><span data-stu-id="e537f-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="e537f-145">Følgende mappebane opprettes automatisk i beholderen:</span><span class="sxs-lookup"><span data-stu-id="e537f-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="e537f-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="e537f-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="e537f-147">Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="e537f-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="e537f-148">*model.json* for de eksporterte enhetene er på *%ExportDestinationName%*-nivået.</span><span class="sxs-lookup"><span data-stu-id="e537f-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="e537f-149">Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="e537f-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="e537f-150">Definer Experience Data Model (XDM) i Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="e537f-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="e537f-151">Før de eksporterte dataene fra målgruppeinnsikt kan brukes i Adobe Experience Platform, må vi definere Experience Data Model-skjemaet og [konfigurere dataene for kundeprofilen i sanntid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="e537f-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="e537f-152">Finn ut [hva XDM er](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) og forstå det [grunnleggende innen skjemakomposisjon](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="e537f-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="e537f-153">Importer data til Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="e537f-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="e537f-154">Nå som alt er klart, må vi importere de klargjorte målgruppedataene fra målgruppeinnsikt til Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e537f-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="e537f-155">Først må du [opprette en Azure Blob Storage-kildetilkobling](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="e537f-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="e537f-156">Når du har definert kildetilkoblingen, må du [konfigurere en dataflyt](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for en skylagringstilkobling for å importere segmentutdataene fra målgruppeinnsikt til Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e537f-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="e537f-157">Opprett en målgruppe i Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e537f-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="e537f-158">Til å sende e-posten for denne kampanjen bruker vi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e537f-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="e537f-159">Når du har importert dataene til Adobe Experience Platform, må vi [opprette en målgruppe](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard ved å bruke dataene i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e537f-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="e537f-160">Lær hvordan du [bruker segmentverktøyet](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) i Adobe Campaign Standard til å definere en målgruppe basert på dataene i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="e537f-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="e537f-161">Opprett og send e-posten ved hjelp av Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e537f-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="e537f-162">Opprett e-postinnholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-posten din.</span><span class="sxs-lookup"><span data-stu-id="e537f-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på e-post med fornyelsestilbud fra Adobe Campaign Standard.":::