---
title: DSR-forespørsler (Data Subject Rights) under GDPR | Microsoft Docs
description: Du kan svare på dataemneforespørsler for målgruppeinnsikt i Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268698"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="cda6a-103">DSR-forespørsler (Data Subject Rights) under GDPR</span><span class="sxs-lookup"><span data-stu-id="cda6a-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="cda6a-104">Svare på forespørsler om å slette GPDR-dataemner for målgruppeinnsikt i Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="cda6a-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="cda6a-105">"Retten til å fjerne" personlige data fra en organisasjons kundedata er en nøkkelbeskyttelse i EUs personvernforordning (GDPR).</span><span class="sxs-lookup"><span data-stu-id="cda6a-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="cda6a-106">Fjerning av personlige data inkluderer fjerning av alle personlige data og systemgenererte logger, unntatt revisjonslogginformasjon.</span><span class="sxs-lookup"><span data-stu-id="cda6a-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="cda6a-107">Behandle slettingsforespørsler for dataemner</span><span class="sxs-lookup"><span data-stu-id="cda6a-107">Manage data subject delete requests</span></span>

<span data-ttu-id="cda6a-108">Målgruppeinnsikt tilbyr følgende produktopplevelser for å slette personlige data for en bestemt kunde eller bruker:</span><span class="sxs-lookup"><span data-stu-id="cda6a-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="cda6a-109">**Behandle sletteforespørsler for kundedata**: Kundedata i Customer Insights er innhentet fra opprinnelige datakilder som ikke er i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cda6a-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="cda6a-110">Alle GDPR-sletteforespørsler må utføres i den opprinnelige datakilden.</span><span class="sxs-lookup"><span data-stu-id="cda6a-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="cda6a-111">**Behandle sletteforespørsler for Customer Insights-brukerdata**: Data for brukere opprettes av Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cda6a-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="cda6a-112">Alle GDPR-sletteforespørsler må utføres i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cda6a-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="cda6a-113">Behandle sletteforespørsler for kundedata</span><span class="sxs-lookup"><span data-stu-id="cda6a-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="cda6a-114">En Customer Insights-administrator kan følge fremgangsmåten nedenfor for å fjerne kundedata som ble slettet i datakilden:</span><span class="sxs-lookup"><span data-stu-id="cda6a-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="cda6a-115">Logg på Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cda6a-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="cda6a-116">I Målgruppeinnsikt går du til **Data** > **Datakilder**</span><span class="sxs-lookup"><span data-stu-id="cda6a-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="cda6a-117">For hver datakilde i listen som inneholder slettede kundedata:</span><span class="sxs-lookup"><span data-stu-id="cda6a-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="cda6a-118">Velg (...) og deretter **Oppdater**.</span><span class="sxs-lookup"><span data-stu-id="cda6a-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="cda6a-119">Kontroller statusen for datakilden under **Status**.</span><span class="sxs-lookup"><span data-stu-id="cda6a-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="cda6a-120">Et merke betyr at oppdateringen var vellykket.</span><span class="sxs-lookup"><span data-stu-id="cda6a-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="cda6a-121">En varseltrekant betyr at noe gikk galt.</span><span class="sxs-lookup"><span data-stu-id="cda6a-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="cda6a-122">Hvis det vises en varseltrekant, kontakter du D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="cda6a-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cda6a-123">![Behandle GDPR-sletteforespørsler for kundedata](media/gdpr-data-sources.png "Behandle GDPR-sletteforespørsler for kundedata")</span><span class="sxs-lookup"><span data-stu-id="cda6a-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="cda6a-124">Behandle sletteforespørsler for brukerdata</span><span class="sxs-lookup"><span data-stu-id="cda6a-124">Manage delete requests for user data</span></span>

<span data-ttu-id="cda6a-125">En Customer Insights-administrator kan følge denne fremgangsmåten for å slette Customer Insights-brukerdata:</span><span class="sxs-lookup"><span data-stu-id="cda6a-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="cda6a-126">Logg på Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cda6a-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="cda6a-127">I Målgruppeinnsikt går du til **Administrasjon** > **Tillatelser**.</span><span class="sxs-lookup"><span data-stu-id="cda6a-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="cda6a-128">Merk av for brukeren du vil slette.</span><span class="sxs-lookup"><span data-stu-id="cda6a-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="cda6a-129">Velg **Fjern**.</span><span class="sxs-lookup"><span data-stu-id="cda6a-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cda6a-130">![Håndtere GPDR-sletteforespørsler for brukerdata](media/gdpr-permissions.png "Håndtere GPDR-sletteforespørsler for brukerdata")</span><span class="sxs-lookup"><span data-stu-id="cda6a-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="cda6a-131">Svare på forespørsler om eksport av GDPR-dataemne</span><span class="sxs-lookup"><span data-stu-id="cda6a-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="cda6a-132">Som en del av vår forpliktelse til å samarbeide med deg om EUs personvernforordning (GDPR), har vi utviklet dokumentasjon som hjelper deg med å forberede deg.</span><span class="sxs-lookup"><span data-stu-id="cda6a-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="cda6a-133">Denne dokumentasjonen beskriver fremgangsmåten du kan bruke i dag for å støtte GDPR-kompatibilitet når du bruker målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="cda6a-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="cda6a-134">Behandle eksport- og visningsforespørsler</span><span class="sxs-lookup"><span data-stu-id="cda6a-134">Manage export and view requests</span></span>

<span data-ttu-id="cda6a-135">Med rettigheten for dataflyttbarhet kan dataemner be om en kopi av personlige data i et elektronisk format (et "strukturert, vanlig brukt, maskinlesbart og kompatibelt format") som kan overføres til en annen datakontroller.</span><span class="sxs-lookup"><span data-stu-id="cda6a-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="cda6a-136">Eksportere kundedata (leieradministrasjon)</span><span class="sxs-lookup"><span data-stu-id="cda6a-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="cda6a-137">En leieradministrator kan følge disse trinnene for å eksportere data:</span><span class="sxs-lookup"><span data-stu-id="cda6a-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="cda6a-138">Send en e-post til D365CI@microsoft.com for å angi kundens e-postadresse i forespørselen.</span><span class="sxs-lookup"><span data-stu-id="cda6a-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="cda6a-139">Customer Insights-teamet sender en e-post til den registrerte e-postadressen til leieradministratoren og ber om bekreftelse på å eksportere data.</span><span class="sxs-lookup"><span data-stu-id="cda6a-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="cda6a-140">Godta bekreftelsen om å eksportere dataene for den forespurte kunden.</span><span class="sxs-lookup"><span data-stu-id="cda6a-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="cda6a-141">Motta de eksporterte dataene via e-postadressen for leieradministratoren.</span><span class="sxs-lookup"><span data-stu-id="cda6a-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="cda6a-142">Eksportere brukerdata (leieradministrasjon)</span><span class="sxs-lookup"><span data-stu-id="cda6a-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="cda6a-143">Send en e-post til D365CI@microsoft.com for å angi brukerens e-postadresse i forespørselen.</span><span class="sxs-lookup"><span data-stu-id="cda6a-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="cda6a-144">Customer Insights-teamet sender en e-post til den registrerte e-postadressen til leieradministratoren og ber om bekreftelse på å eksportere data.</span><span class="sxs-lookup"><span data-stu-id="cda6a-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="cda6a-145">Godta bekreftelsen om å eksportere dataene for den forespurte brukeren.</span><span class="sxs-lookup"><span data-stu-id="cda6a-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="cda6a-146">Motta de eksporterte dataene via e-postadressen for leieradministratoren.</span><span class="sxs-lookup"><span data-stu-id="cda6a-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]