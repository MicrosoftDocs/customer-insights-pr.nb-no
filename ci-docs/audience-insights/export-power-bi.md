---
title: Power BI-kobling
description: Finn ut hvordan du bruker Dynamics 365 Customer Insights-koblingen i Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406496"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="d24eb-103">Kobling for Power BI (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="d24eb-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="d24eb-104">Opprett visualiseringer for dataene med Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="d24eb-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="d24eb-105">Generer ekstra innsikter og bygg rapporter med enhetlige kundedata.</span><span class="sxs-lookup"><span data-stu-id="d24eb-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d24eb-106">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="d24eb-106">Prerequisites</span></span>

- <span data-ttu-id="d24eb-107">Du har enhetlige kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="d24eb-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="d24eb-108">Den nyeste versjonen av [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) er installert på datamaskinen.</span><span class="sxs-lookup"><span data-stu-id="d24eb-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="d24eb-109">[Lær mer om Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="d24eb-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="d24eb-110">Konfigurer koblingen for Power BI</span><span class="sxs-lookup"><span data-stu-id="d24eb-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="d24eb-111">I Power BI Desktop velger du **Fil** > **Hent data**.</span><span class="sxs-lookup"><span data-stu-id="d24eb-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="d24eb-112">Velg **Se mer** og søk etter **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="d24eb-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="d24eb-113">Velg resultatet, og velg **Koble til**.</span><span class="sxs-lookup"><span data-stu-id="d24eb-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="d24eb-114">**Logg på** med samme organisasjonskonto som du bruker for Customer Insights, og velg **Koble til**.</span><span class="sxs-lookup"><span data-stu-id="d24eb-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="d24eb-115">Kontoen du angir i dette trinnet, brukes til å hente data fra Customer Insights og trenger ikke være den samme som du er logget på Power BI.</span><span class="sxs-lookup"><span data-stu-id="d24eb-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="d24eb-116">Hvis du vil tilbakestille kontoen som brukes til datainnhenting, åpner du Power BI og går til **Fil** > **Alternativer** > **Instillinger** > **Datakildeinnstillinger**.</span><span class="sxs-lookup"><span data-stu-id="d24eb-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="d24eb-117">I listen over datakilder velger du **Dynamics 365 Customer Insights-pålogging** og deretter **Fjern tillatelser**.</span><span class="sxs-lookup"><span data-stu-id="d24eb-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="d24eb-118">I **Navigator**-dialogboksen.</span><span class="sxs-lookup"><span data-stu-id="d24eb-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="d24eb-119">Du ser listen over alle miljøer som du har tilgang til.</span><span class="sxs-lookup"><span data-stu-id="d24eb-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="d24eb-120">Utvid et miljø, og åpne en av mappene (enheter, mål, segmenter, suppleringer).</span><span class="sxs-lookup"><span data-stu-id="d24eb-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="d24eb-121">Åpne for eksempel **Enheter**-mappen for å se alle enhetene du kan importere.</span><span class="sxs-lookup"><span data-stu-id="d24eb-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="d24eb-122">![Power BI-koblingsnavigator](media/power-bi-navigator.png "Power BI-koblingsnavigator")</span><span class="sxs-lookup"><span data-stu-id="d24eb-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="d24eb-123">Merk av i avmerkingsboksene ved siden av enhetene som skal inkluderes, og velg **Last inn**.</span><span class="sxs-lookup"><span data-stu-id="d24eb-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="d24eb-124">Du kan velge flere enheter fra flere miljøer.</span><span class="sxs-lookup"><span data-stu-id="d24eb-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="d24eb-125">Det vises en dialogboks for innlasting når enhetene lastes inn.</span><span class="sxs-lookup"><span data-stu-id="d24eb-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="d24eb-126">Når alle de valgte enhetene er lastet, kan du bruke funksjonene i Power BI til å visualisere dataene.</span><span class="sxs-lookup"><span data-stu-id="d24eb-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="d24eb-127">Store datasett</span><span class="sxs-lookup"><span data-stu-id="d24eb-127">Large data sets</span></span>

<span data-ttu-id="d24eb-128">Customer Insights-koblingen for Power BI er utformet for å fungere for datasett som inneholder opptil 1 000 000 kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="d24eb-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="d24eb-129">Det kan hende at importen av større datasett fungerer, men det krever lang tid.</span><span class="sxs-lookup"><span data-stu-id="d24eb-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="d24eb-130">Prosessen kan også bli tidsavbrutt på grunn av Power BI-begrensninger.</span><span class="sxs-lookup"><span data-stu-id="d24eb-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="d24eb-131">Hvis du vil ha mer informasjon, kan du se [Power BI: Anbefalinger for store datasett](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="d24eb-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="d24eb-132">Arbeide med et delsett av data</span><span class="sxs-lookup"><span data-stu-id="d24eb-132">Work with a subset of data</span></span>

<span data-ttu-id="d24eb-133">Vurder å arbeide med et delsett av dataene.</span><span class="sxs-lookup"><span data-stu-id="d24eb-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="d24eb-134">Du kan for eksempel opprette [segmenter](segments.md) i stedet for å eksportere alle kundeoppføringer til Power BI.</span><span class="sxs-lookup"><span data-stu-id="d24eb-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
