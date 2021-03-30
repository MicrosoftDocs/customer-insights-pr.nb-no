---
title: Koble til enheter i den administrerte Common Data Service-sjøen
description: Importer data fra et Common Data Service-administrert datasjø.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596971"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="6aa2a-103">Koble til data i en Common Data Service-administrert datasjø</span><span class="sxs-lookup"><span data-stu-id="6aa2a-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6aa2a-104">Denne artikkelen inneholder informasjon om hvordan eksisterende Dynamics 365-kunder raskt kan koble seg til sine analytiske enheter i den Common Data Service-administrerte datasjøen.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="6aa2a-105">Du må være administrator i Common Data Service-organisasjonen for å fortsette og vise listen over enheter som er tilgjengelige i den administrerte datasjøen.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="6aa2a-106">Viktige hensyn</span><span class="sxs-lookup"><span data-stu-id="6aa2a-106">Important considerations</span></span>

<span data-ttu-id="6aa2a-107">Data som lagres i onlinetjenester, for eksempel Azure Data Lake Storage, kan lagres på et annet sted enn der data behandles eller lagres i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="6aa2a-108">Ved å importere eller koble til data som er lagret i en onlinetjeneste, godtar du at dataene kan overføres til og lagres med Dynamics 365 Customer Insights. [Finn ut mer på Microsoft Klareringssenter.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="6aa2a-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="6aa2a-109">Koble til en Common Data Service-administrert sjø</span><span class="sxs-lookup"><span data-stu-id="6aa2a-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="6aa2a-110">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6aa2a-111">Velg **Legg til datakilde**.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="6aa2a-112">Velg **Koble til Common Data Service**, og velg deretter **Neste**.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="6aa2a-113">Skriv inn et **navn** for datakilden, og klikk deretter **Neste**.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="6aa2a-114">Navneretningslinjer:</span><span class="sxs-lookup"><span data-stu-id="6aa2a-114">Name guidelines:</span></span> 
   - <span data-ttu-id="6aa2a-115">Start med en bokstav.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-115">Start with a letter.</span></span>
   - <span data-ttu-id="6aa2a-116">Bruk bare bokstaver og tall.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-116">Use letters and numbers only.</span></span> <span data-ttu-id="6aa2a-117">Spesialtegn og mellomrom er ikke tillatt.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="6aa2a-118">Bruk mellom 3 og 64 tegn.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="6aa2a-119">Angi **serveradressen** for Common Data Service-organisasjonen, og velg **Logg på**.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6aa2a-120">![Dialogboks for å skrive inn Common Data Service-serveradresse](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="6aa2a-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="6aa2a-121">Velg enhetene du vil ta inn, fra den tilgjengelige listen.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="6aa2a-122">Hvis noen enheter allerede er valgt, kan de brukes av andre Dynamics 365-programmer (for eksempel Dynamics 365 Sales Insights eller Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="6aa2a-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="6aa2a-123">Du kan ikke endre valget.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-123">You can't change the selection.</span></span> <span data-ttu-id="6aa2a-124">Disse enhetene vil være tilgjengelige når datakilden er opprettet.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6aa2a-125">![Dialogboks som viser en liste over enheter i Common Data Service-organisasjonen](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="6aa2a-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="6aa2a-126">Lagre valget for å starte synkronisering av de valgte enhetene til den Common Data Service-administrerte sjøen.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="6aa2a-127">Du finner den nylig tillagte koblingen på **Datakilder**-siden.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="6aa2a-128">Det blir lagt i kø for oppdatering, og antallet enheter vises som 0 til alle enhetene er synkronisert.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="6aa2a-129">Bare én datakilde av et miljø som kan bruke samme administrerte Common Data Service-sjø samtidig.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="6aa2a-130">Redigere en datakilde for Common Data Service-administrert sjø</span><span class="sxs-lookup"><span data-stu-id="6aa2a-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="6aa2a-131">Du redigerer bare enhetsvalget etter opprettelsen av datakilden.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="6aa2a-132">For eksempel hvis flere enheter ble lagt til i Common Data Service, og du vil importere dem også.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="6aa2a-133">Hvis du vil koble til en annen Common Data Service, [oppretter du en ny datakilde](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="6aa2a-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="6aa2a-134">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6aa2a-135">Klikk ellipsen ved siden av datakilden du vil oppdatere.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="6aa2a-136">Velg **Rediger**-alternativet fra listen.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="6aa2a-137">Velg flere enheter fra den tilgjengelige listen med enheter, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="6aa2a-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]