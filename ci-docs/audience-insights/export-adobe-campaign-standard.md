---
title: Eksporter Customer Insights-data til Adobe Campaign Standard
description: Lær hvordan du bruker målgruppeinnsiktssegmenter i Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596327"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="fda82-103">Bruk Customer Insights-segmenter i Adobe Campaign Standard (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="fda82-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="fda82-104">Som bruker av målgruppeinnsikt for Dynamics 365 Customer Insights har du kanskje opprettet segmenter for å gjøre markedsføringskampanjene mer effektive ved å rette deg mot relevante målgrupper.</span><span class="sxs-lookup"><span data-stu-id="fda82-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="fda82-105">Hvis du vil bruke et segment fra målgruppeinnsikt i Adobe Experience Platform og programmer som Adobe Campaign Standard, må du følge noen få trinn som er beskrevet i denne artikkelen.</span><span class="sxs-lookup"><span data-stu-id="fda82-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Prosessdiagram for trinnene beskrevet i denne artikkelen.":::

## <a name="prerequisites"></a><span data-ttu-id="fda82-107">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="fda82-107">Prerequisites</span></span>

-   <span data-ttu-id="fda82-108">Dynamics 365 Customer Insights-lisens</span><span class="sxs-lookup"><span data-stu-id="fda82-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="fda82-109">Adobe Campaign Standard-lisens</span><span class="sxs-lookup"><span data-stu-id="fda82-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="fda82-110">Azure Blob Storage-konto</span><span class="sxs-lookup"><span data-stu-id="fda82-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="fda82-111">Kampanjeoversikt</span><span class="sxs-lookup"><span data-stu-id="fda82-111">Campaign Overview</span></span>

<span data-ttu-id="fda82-112">For en bedre forståelse av hvordan du kan bruke segmenter fra målgruppeinnsikt i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampanje.</span><span class="sxs-lookup"><span data-stu-id="fda82-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="fda82-113">La oss anta at firmaet ditt tilbyr en månedlig abonnementsbasert tjeneste til kundene i USA.</span><span class="sxs-lookup"><span data-stu-id="fda82-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="fda82-114">Du ønsker å identifisere kunder som har abonnementer som skal fornyes i løpet av de neste åtte dagene, men som ennå ikke har fornyet abonnementet.</span><span class="sxs-lookup"><span data-stu-id="fda82-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="fda82-115">Hvis du vil beholde disse kundene, må du sende dem et kampanjetilbud via e-post ved hjelp av Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="fda82-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="fda82-116">I dette eksemplet skal vi kjøre den promoterende e-postkampanjen én gang.</span><span class="sxs-lookup"><span data-stu-id="fda82-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="fda82-117">Denne artikkelen dekker ikke brukstilfellet for kjøring av kampanjen flere ganger.</span><span class="sxs-lookup"><span data-stu-id="fda82-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="fda82-118">Målgruppeinnsikt og Adobe Campaign Standard kan imidlertid konfigureres til også å fungere for et gjentakende kampanjescenario.</span><span class="sxs-lookup"><span data-stu-id="fda82-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="fda82-119">Identifiser målgruppen</span><span class="sxs-lookup"><span data-stu-id="fda82-119">Identify your target audience</span></span>

<span data-ttu-id="fda82-120">I vårt scenario antar vi at e-postadressene til kundene er tilgjengelige i målgruppeinnsikt, og at kampanjepreferansene deres ble analysert for å identifisere medlemmer i segmentet.</span><span class="sxs-lookup"><span data-stu-id="fda82-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="fda82-121">[Segmentet du definerte i målgruppeinnsikt](segments.md), kalles **ChurnProneCustomers**, og du planlegger å sende e-postkampanjen til disse kundene.</span><span class="sxs-lookup"><span data-stu-id="fda82-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skjermbilde av segmentsiden med ChurnProneCustomers -segmentet opprettet.":::

<span data-ttu-id="fda82-123">E-postmeldingen for tilbudet du vil sende ut, inneholder kundens fornavn, etternavn og sluttdatoen for abonnementet.</span><span class="sxs-lookup"><span data-stu-id="fda82-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="fda82-124">Den informerer kundene om rabatten de får hvis de fornyer abonnementet før abonnementet avsluttes.</span><span class="sxs-lookup"><span data-stu-id="fda82-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="fda82-125">Eksporter målgruppen</span><span class="sxs-lookup"><span data-stu-id="fda82-125">Export your target audience</span></span>

<span data-ttu-id="fda82-126">Når målgruppen er identifisert, kan vi konfigurere eksporten fra målgruppeinnsikt til en Azure Blob Storage-konto.</span><span class="sxs-lookup"><span data-stu-id="fda82-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="fda82-127">I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="fda82-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fda82-128">I flisen **Adobe-kampanje** velger du **Oppsett**.</span><span class="sxs-lookup"><span data-stu-id="fda82-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurasjonsflis for Adobe Campaign Standard.":::

1. <span data-ttu-id="fda82-130">Angi et **visningsnavn** for dette nye eksportmålet, og angi deretter **kontonavnet**, **kontonøkkelen** og **beholderen** for Azure Blob Storage-kontoen du vil eksportere segmentet til.</span><span class="sxs-lookup"><span data-stu-id="fda82-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skjermbilde av konfigurasjonen av lagringskontoen. "::: 

   - <span data-ttu-id="fda82-132">Hvis du vil vite mer om hvordan du finner navnet og nøkkelen til Azure Blob Storage-kontoen, kan du se [Administrere lagringskontoinnstillinger i Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="fda82-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="fda82-133">Hvis du vil lære hvordan du oppretter en beholder, kan du se [Opprette en beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="fda82-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="fda82-134">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="fda82-134">Select **Next**.</span></span>

1. <span data-ttu-id="fda82-135">Velg segmentet du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="fda82-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="fda82-136">I dette eksemplet er det **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="fda82-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skjermbilde av brukergrensesnittet for segmentvalg med ChurnProneCustomers-segmentet valgt.":::

1. <span data-ttu-id="fda82-138">Velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="fda82-138">Select **Next**.</span></span>

1. <span data-ttu-id="fda82-139">Nå tilordner vi **Kilde**-feltene fra målgruppeinnsiktssegmentet til **Mål**-feltnavnene i Adobe Campaign Standard-profilskjemaet.</span><span class="sxs-lookup"><span data-stu-id="fda82-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Felttilordning for Adobe Campaign Standard-koblingen.":::

   <span data-ttu-id="fda82-141">Hvis du vil legge til flere attributter, velger du **Legg til attributt**.</span><span class="sxs-lookup"><span data-stu-id="fda82-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="fda82-142">Målnavnet kan være et annet enn kildefeltnavnet, slik at du fremdeles kan tilordne segmentutdata fra målgruppeinnsikt til Adobe Campaign Standard hvis feltene ikke har samme navn i de to systemene.</span><span class="sxs-lookup"><span data-stu-id="fda82-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fda82-143">E-postadressen brukes som et identitetsfelt, men du kan bruke alle andre identifikatorer fra målgruppeinnsikt til å tilordne data til Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="fda82-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="fda82-144">Velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="fda82-144">Select **Save**.</span></span>

<span data-ttu-id="fda82-145">Når du har lagret eksportmålet, finner du det i **Administrator** > **Eksporter** > **Mine eksportmål**.</span><span class="sxs-lookup"><span data-stu-id="fda82-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Skjermbilde med listen over eksporter og eksempelsegment uthevet.":::

<span data-ttu-id="fda82-147">Du kan nå [eksportere segmentet ved behov](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fda82-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="fda82-148">Eksporten blir også kjørt med hver [planlagte oppdatering](system.md).</span><span class="sxs-lookup"><span data-stu-id="fda82-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fda82-149">Kontroller at antall oppføringer i det eksporterte segmentet er innenfor den tillatte grensen for Adobe Campaign Standard-lisensen.</span><span class="sxs-lookup"><span data-stu-id="fda82-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="fda82-150">Eksporterte data lagres i Azure Blob Storage-beholderen du konfigurerte ovenfor.</span><span class="sxs-lookup"><span data-stu-id="fda82-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="fda82-151">Følgende mappebane opprettes automatisk i beholderen:</span><span class="sxs-lookup"><span data-stu-id="fda82-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="fda82-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="fda82-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="fda82-153">Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="fda82-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="fda82-154">Konfigurer Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fda82-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="fda82-155">Når et segment fra målgruppeinnsikt eksporteres, inneholder det kolonnene du valgte da du definerte eksportmålet i forrige trinn.</span><span class="sxs-lookup"><span data-stu-id="fda82-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="fda82-156">Disse dataene kan brukes til å [opprette profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="fda82-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="fda82-157">Hvis du vil bruke segmentet i Adobe Campaign Standard, må vi utvide profilskjemaet i Adobe Campaign Standard til å inkludere to tilleggsfelter.</span><span class="sxs-lookup"><span data-stu-id="fda82-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="fda82-158">Lær hvordan du [utvider profilressursen](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) med nye felt i Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="fda82-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="fda82-159">I vårt eksempel er disse feltene *Segmentnavn og Segmentdato (valgfritt).*</span><span class="sxs-lookup"><span data-stu-id="fda82-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="fda82-160">Vi skal bruke disse feltene til å identifisere profilene i Adobe Campaign Standard som vi vil målrette for denne kampanjen.</span><span class="sxs-lookup"><span data-stu-id="fda82-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="fda82-161">Hvis det ikke finnes andre oppføringer i Adobe Campaign Standard enn den du skal importere, kan du hoppe over dette trinnet.</span><span class="sxs-lookup"><span data-stu-id="fda82-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="fda82-162">Importer data til Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fda82-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="fda82-163">Nå som alt er klart, må vi importere de klargjorte målgruppedataene fra målgruppeinnsikt til Adobe Campaign Standard for å opprette profiler.</span><span class="sxs-lookup"><span data-stu-id="fda82-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="fda82-164">Lær [hvordan du importerer profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) ved hjelp av en arbeidsflyt.</span><span class="sxs-lookup"><span data-stu-id="fda82-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="fda82-165">Importarbeidsflyten i bildet nedenfor er konfigurert til å kjøre hver 8. time og ser etter eksporterte målgruppeinnsiktssegmenter (CSV-fil i Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="fda82-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="fda82-166">Arbeidsflyten pakker ut CSV-filinnholdet i en bestemt kolonnerekkefølge.</span><span class="sxs-lookup"><span data-stu-id="fda82-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="fda82-167">Denne arbeidsflyten er bygget for å utføre grunnleggende feilhåndtering og sikre at hver oppføring har en e-postadresse før dataene samles inn i Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="fda82-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="fda82-168">Arbeidsflyten pakker også ut segmentnavnet fra filnavnet før det blir satt opp i ACS-profildata.</span><span class="sxs-lookup"><span data-stu-id="fda82-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Skjermbilde av en importarbeidsflyt i brukergrensesnittet til Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="fda82-170">Hent målgruppen i Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fda82-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="fda82-171">Når dataene er importert til Adobe Campaign Standard, kan du [opprette en arbeidsflyt](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) og [spørre](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) kundene basert på *Segmentnavn* og *Segmentdato* for å velge profiler som ble identifisert for eksempelkampanjen vår.</span><span class="sxs-lookup"><span data-stu-id="fda82-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="fda82-172">Opprett og send e-posten ved hjelp av Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fda82-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="fda82-173">Opprett e-postinnholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-posten din.</span><span class="sxs-lookup"><span data-stu-id="fda82-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på e-post med fornyelsestilbud fra Adobe Campaign Standard.":::