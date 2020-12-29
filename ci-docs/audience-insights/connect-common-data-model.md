---
title: Koble Common Data Model-til en Azure Data Lake-konto
description: Arbeid med Common Data Model-data ved hjelp av Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643470"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="7d5e0-103">Knytte til en Common Data Model-mappe ved å bruke en Azure Data Lake-konto</span><span class="sxs-lookup"><span data-stu-id="7d5e0-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="7d5e0-104">Denne artikkelen inneholder informasjon om hvordan du tar inn data fra en Common Data Model-mappe ved hjelp av en Azure Data Lake Storage Gen2-konto.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="7d5e0-105">Viktige hensyn</span><span class="sxs-lookup"><span data-stu-id="7d5e0-105">Important considerations</span></span>

- <span data-ttu-id="7d5e0-106">Data i Azure Data Lake må følge Common Data Model-standarden.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="7d5e0-107">Andre formater støttes ikke for øyeblikket.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="7d5e0-108">Datainntak støtter kun Azure Data Lake *Gen2*-lagringskontoer.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="7d5e0-109">Du kan ikke bruke Azure Data Lake Gen1-lagringskontoer til å ta inn data.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="7d5e0-110">Når du skal godkjenne med en Azure-tjenestekontohaver, må den være konfigurert i leieren.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="7d5e0-111">Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="7d5e0-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="7d5e0-112">Azure Data Lake-forekomsten du vil koble til og ta inn data fra, må være i samme Azure-område som Dynamics 365 Customer Insights-miljøet.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="7d5e0-113">Tilkoblinger til en Common Data Model-mappe fra en Data Lake-forekomst i et annet Azure-område støttes ikke.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="7d5e0-114">Hvis du vil vite Azure-området i miljøet, går du til **Administrasjon** > **System** > **Om** i Målgruppeinnsikt.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="7d5e0-115">Data som er lagret i onlinetjenester, kan lagres på en annen plassering enn der data behandles eller lagres i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="7d5e0-116">Ved å importere eller koble til data som er lagret i en onlinetjeneste, godtar du at dataene kan overføres til og lagres med Dynamics 365 Customer Insights. [Finn ut mer på Microsoft Klareringssenter.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="7d5e0-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="7d5e0-117">Koble til en mappe i Common Data Model</span><span class="sxs-lookup"><span data-stu-id="7d5e0-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="7d5e0-118">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="7d5e0-119">Velg **Legg til datakilde**.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="7d5e0-120">Velg **Koble til en mappe i Common Data Model**, angi et **navn** for datakilden, og velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="7d5e0-121">Du kan velge mellom å bruke et ressursbasert alternativ og et abonnementsbasert alternativ for godkjenning.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="7d5e0-122">Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="7d5e0-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="7d5e0-123">Skriv inn informasjon om **beholderen**, og velg **Neste**.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7d5e0-124">![Dialogboks for å angi tilkoblingsdetaljer for Azure Data Lake](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="7d5e0-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="7d5e0-125">I dialogboksen **Velg en mappe i Common Data Model** velger du model.json-filen du vil importere data fra, og velger deretter **Neste**.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="7d5e0-126">En model.json-fil som er tilknyttet en annen datakilde i miljøet, vises ikke i listen.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="7d5e0-127">Det vises en liste over tilgjengelige enheter i den valgte model.json-filen.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="7d5e0-128">Du kan se gjennom og velge fra listen over tilgjengelige enheter, og deretter velge **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="7d5e0-129">Alle de valgte enhetene tas inn fra den nye datakilden.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7d5e0-130">![Dialogboks som viser en liste over enheter fra en model.json-fil](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="7d5e0-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="7d5e0-131">Angi hvilke dataenheter du vil aktivere dataprofilering for, og velg **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="7d5e0-132">Dataprofilering aktiverer analyse og andre funksjoner.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="7d5e0-133">Du kan velge hele enheten, noe som velger alle attributter fra enheten, eller du kan velge bestemte valgte attributter.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="7d5e0-134">Som standard er ingen enheter aktivert for dataprofilering.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7d5e0-135">![Dialogboks som viser dataprofilering](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="7d5e0-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="7d5e0-136">Når du har lagret valgene, åpnes siden **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="7d5e0-137">Nå skal du se Common Data Model-mappen som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="7d5e0-138">En model.json-fil kan bare tilknyttes én datakilde i samme miljø.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="7d5e0-139">Den samme model.json-filen kan imidlertid brukes for datakilder i flere miljøer.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="7d5e0-140">Redigere en datakilde for Common Data Model-mappe</span><span class="sxs-lookup"><span data-stu-id="7d5e0-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="7d5e0-141">Du kan oppdatere tilgangsnøkkelen for lagringskontoen som inneholder Common Data Model-mappen.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="7d5e0-142">Du kan også endre model.json-filen.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-142">You may also change the model.json file.</span></span> <span data-ttu-id="7d5e0-143">Hvis du vil koble til en annen beholder fra lagringskontoen, eller endre navnet på forretningsforbindelsen, må du [opprette en ny datakilde-tilkobling](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="7d5e0-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="7d5e0-144">I Målgruppeinnsikt går du til **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="7d5e0-145">Klikk ellipsen ved siden av datakilden du vil oppdatere.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="7d5e0-146">Velg **Rediger**-alternativet fra listen.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="7d5e0-147">Du kan eventuelt oppdatere **tilgangsnøkkelen** og velge **Neste**.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialogboks for å redigere og oppdatere en tilgangstast for en eksisterende datakilde](media/edit-access-key.png)

5. <span data-ttu-id="7d5e0-149">Du kan eventuelt oppdatere fra en kontonøkkeltilkobling til en ressursbasert eller abonnementsbasert tilkobling.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="7d5e0-150">Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="7d5e0-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="7d5e0-151">Du kan ikke endre informasjon om en **beholder** når du oppdaterer tilkoblingen.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7d5e0-152">![Dialogboks for å angi tilkoblingsdetaljer for Azure Data Lake](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="7d5e0-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="7d5e0-153">Du kan også velge en annen model.json-fil med et annet sett med enheter fra beholderen.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="7d5e0-154">Alternativt kan du velge flere enheter å ta inn.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="7d5e0-155">Du kan også fjerne eventuelle enheter som allerede er valgt, hvis det ikke finnes avhengigheter.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="7d5e0-156">Hvis det er avhengigheter i den eksisterende model.json-filen og enhetssettet, vises en feilmelding, og du kan ikke velge en annen model.json-fil.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="7d5e0-157">Fjern avhengighetene før du endrer model.json-filen, eller opprett en ny datakilde med model.json-filen du vil bruke, for å unngå å fjerne avhengighetene.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="7d5e0-158">Du kan også velge flere attributter eller enheter du vil aktivere dataprofilering på eller deaktivere en som allerede er valgt.</span><span class="sxs-lookup"><span data-stu-id="7d5e0-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
