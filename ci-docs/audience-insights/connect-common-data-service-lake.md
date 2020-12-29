---
title: Koble til enheter i den administrerte Common Data Service-sjøen
description: Importer data fra et Common Data Service-administrert datasjø.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643410"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="830bf-103">Koble til data i en Common Data Service-administrert datasjø</span><span class="sxs-lookup"><span data-stu-id="830bf-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="830bf-104">Denne artikkelen inneholder informasjon om hvordan eksisterende Dynamics 365-kunder raskt kan koble seg til sine analytiske enheter i den Common Data Service-administrerte datasjøen.</span><span class="sxs-lookup"><span data-stu-id="830bf-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="830bf-105">Du må være administrator i Common Data Service-organisasjonen for å fortsette og vise listen over enheter som er tilgjengelige i den administrerte datasjøen.</span><span class="sxs-lookup"><span data-stu-id="830bf-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="830bf-106">Viktige hensyn</span><span class="sxs-lookup"><span data-stu-id="830bf-106">Important considerations</span></span>

<span data-ttu-id="830bf-107">Data som lagres i onlinetjenester, for eksempel Azure Data Lake Storage, kan lagres på et annet sted enn der data behandles eller lagres i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="830bf-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="830bf-108">Ved å importere eller koble til data som er lagret i en onlinetjeneste, godtar du at dataene kan overføres til og lagres med Dynamics 365 Customer Insights. [Finn ut mer på Microsoft Klareringssenter.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="830bf-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="830bf-109">Koble til en Common Data Service-administrert sjø</span><span class="sxs-lookup"><span data-stu-id="830bf-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="830bf-110">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="830bf-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="830bf-111">Velg **Legg til datakilde**.</span><span class="sxs-lookup"><span data-stu-id="830bf-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="830bf-112">Velg **Koble til Common Data Service**, og velg deretter **Neste**.</span><span class="sxs-lookup"><span data-stu-id="830bf-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="830bf-113">Skriv inn et **navn** for datakilden, og klikk deretter **Neste**.</span><span class="sxs-lookup"><span data-stu-id="830bf-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="830bf-114">Angi **serveradressen** for Common Data Service-organisasjonen, og velg **Logg på**.</span><span class="sxs-lookup"><span data-stu-id="830bf-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="830bf-115">![Dialogboks for å skrive inn Common Data Service-serveradresse](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="830bf-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="830bf-116">Velg enhetene du vil ta inn, fra den tilgjengelige listen.</span><span class="sxs-lookup"><span data-stu-id="830bf-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="830bf-117">Hvis noen enheter allerede er valgt, kan de brukes av andre Dynamics 365-programmer (for eksempel Dynamics 365 Sales Insights eller Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="830bf-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="830bf-118">Du kan ikke endre valget.</span><span class="sxs-lookup"><span data-stu-id="830bf-118">You can't change the selection.</span></span> <span data-ttu-id="830bf-119">Disse enhetene vil være tilgjengelige når datakilden er opprettet.</span><span class="sxs-lookup"><span data-stu-id="830bf-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="830bf-120">![Dialogboks som viser en liste over enheter i Common Data Service-organisasjonen](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="830bf-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="830bf-121">Lagre valget for å starte synkronisering av de valgte enhetene til den Common Data Service-administrerte sjøen.</span><span class="sxs-lookup"><span data-stu-id="830bf-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="830bf-122">Du finner den nylig tillagte koblingen på **Datakilder**-siden.</span><span class="sxs-lookup"><span data-stu-id="830bf-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="830bf-123">Det blir lagt i kø for oppdatering, og antallet enheter vises som 0 til alle enhetene er synkronisert.</span><span class="sxs-lookup"><span data-stu-id="830bf-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="830bf-124">Bare én datakilde av et miljø som kan bruke samme administrerte Common Data Service-sjø samtidig.</span><span class="sxs-lookup"><span data-stu-id="830bf-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="830bf-125">Redigere en datakilde for Common Data Service-administrert sjø</span><span class="sxs-lookup"><span data-stu-id="830bf-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="830bf-126">Du redigerer bare enhetsvalget etter opprettelsen av datakilden.</span><span class="sxs-lookup"><span data-stu-id="830bf-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="830bf-127">For eksempel hvis flere enheter ble lagt til i Common Data Service, og du vil importere dem også.</span><span class="sxs-lookup"><span data-stu-id="830bf-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="830bf-128">Hvis du vil koble til en annen Common Data Service, [oppretter du en ny datakilde](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="830bf-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="830bf-129">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="830bf-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="830bf-130">Klikk ellipsen ved siden av datakilden du vil oppdatere.</span><span class="sxs-lookup"><span data-stu-id="830bf-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="830bf-131">Velg **Rediger**-alternativet fra listen.</span><span class="sxs-lookup"><span data-stu-id="830bf-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="830bf-132">Velg flere enheter fra den tilgjengelige listen med enheter, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="830bf-132">Select additional entities from the available list of entities and select **Save**.</span></span>
