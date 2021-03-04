---
title: Supplering med egendefinert SFTP-import
description: Generell informasjon om supplering med egendefinert SFTP-import.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269618"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="bdb18-103">Supplere kundeprofiler med egendefinerte data (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="bdb18-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="bdb18-104">Med egendefinert SFTP-import (Secure File Transfer Protocol) kan du importere data som ikke trenger å gå gjennom dataforening.</span><span class="sxs-lookup"><span data-stu-id="bdb18-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="bdb18-105">Det er en fleksibel, sikker og enkel måte å skaffe seg på dataene på.</span><span class="sxs-lookup"><span data-stu-id="bdb18-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="bdb18-106">Egendefinert SFTP-import kan brukes i kombinasjon med [SFTP-eksport](export-sftp.md), noe som gjør at du kan eskportere kundeprofildataene som er nødvendig for supplering.</span><span class="sxs-lookup"><span data-stu-id="bdb18-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="bdb18-107">Dataene kan deretter behandles og suppleres, og den egendefinerte SFTP-importen kan brukes til å hente de supplerte dataene tilbake til målgruppeinnsikt i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bdb18-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bdb18-108">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="bdb18-108">Prerequisites</span></span>

<span data-ttu-id="bdb18-109">For å konfigure egendefinert SFTP-import må følgende forhåndskrav være oppfylt:</span><span class="sxs-lookup"><span data-stu-id="bdb18-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="bdb18-110">Du har brukerlegitimasjon (brukernavn og passord) for SFTP-plasseringen der dataene som skal importeres, ligger.</span><span class="sxs-lookup"><span data-stu-id="bdb18-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="bdb18-111">Du har URL-adressen og portnummeret (vanligvis 22) for STFP-verten.</span><span class="sxs-lookup"><span data-stu-id="bdb18-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="bdb18-112">Du har filnavnet og plasseringen til filen som skal importeres på SFTP-verten.</span><span class="sxs-lookup"><span data-stu-id="bdb18-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="bdb18-113">Det finnes en *model.json*-fil som angir skjemaet for dataene som skal importeres.</span><span class="sxs-lookup"><span data-stu-id="bdb18-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="bdb18-114">Denne filen må være i samme katalog som filen som skal importeres.</span><span class="sxs-lookup"><span data-stu-id="bdb18-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="bdb18-115">Du har [administratortillatelser](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="bdb18-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="bdb18-116">Konfigurasjon</span><span class="sxs-lookup"><span data-stu-id="bdb18-116">Configuration</span></span>

1. <span data-ttu-id="bdb18-117">Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.</span><span class="sxs-lookup"><span data-stu-id="bdb18-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="bdb18-118">På **flisen for egendefinert SFTP-import** velger du **Suppler dataene**.</span><span class="sxs-lookup"><span data-stu-id="bdb18-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bdb18-119">![Flis for egendefinert SFTP-import](media/SFTP_Custom_Import_tile.png "Flis for egendefinert SFTP-import")</span><span class="sxs-lookup"><span data-stu-id="bdb18-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="bdb18-120">Velg **Kom i gang**, og angi legitimasjonen og adressen for SFTP-serveren.</span><span class="sxs-lookup"><span data-stu-id="bdb18-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="bdb18-121">Eksempel: sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="bdb18-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="bdb18-122">Skriv inn navnet på filen som inneholder dataene, og banen til filen på SFTP-serveren hvis den ikke finnes i rotmappen.</span><span class="sxs-lookup"><span data-stu-id="bdb18-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="bdb18-123">Bekreft alle inndata ved å velge **Koble til egendefinert import**.</span><span class="sxs-lookup"><span data-stu-id="bdb18-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bdb18-124">![Undermeny for konfigurasjon av egendefinert SFTP-import](media/SFTP_Custom_Import_Configuration_flyout.png "Undermeny for konfigurasjon av egendefinert SFTP-import")</span><span class="sxs-lookup"><span data-stu-id="bdb18-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="bdb18-125">Definere felttilordninger</span><span class="sxs-lookup"><span data-stu-id="bdb18-125">Defining field mappings</span></span> 

<span data-ttu-id="bdb18-126">Katalogen som inneholder filen som skal importeres på SFTP-serveren, må også inneholde en *model.json*-fil.</span><span class="sxs-lookup"><span data-stu-id="bdb18-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="bdb18-127">Denne filen definerer skjemaet som skal brukes til å importere dataene.</span><span class="sxs-lookup"><span data-stu-id="bdb18-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="bdb18-128">Skjemaet må bruke [Common Data Model](https://docs.microsoft.com/common-data-model/) for å angi felttilordningen.</span><span class="sxs-lookup"><span data-stu-id="bdb18-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="bdb18-129">Et enkelt eksempel på en model.json-fil ser slik ut:</span><span class="sxs-lookup"><span data-stu-id="bdb18-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="bdb18-130">Resultater av supplering</span><span class="sxs-lookup"><span data-stu-id="bdb18-130">Enrichment results</span></span>

<span data-ttu-id="bdb18-131">Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="bdb18-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="bdb18-132">Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bdb18-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bdb18-133">Behandlingstiden avhenger av størrelsen på dataene som skal importeres, og tilkoblingen til SFTP-serveren.</span><span class="sxs-lookup"><span data-stu-id="bdb18-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="bdb18-134">Når suppleringsprosessen er fullført, kan du se gjennom de nylig importerte egendefinerte suppleringsdataene under **Mine suppleringer**.</span><span class="sxs-lookup"><span data-stu-id="bdb18-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="bdb18-135">I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.</span><span class="sxs-lookup"><span data-stu-id="bdb18-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bdb18-136">Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.</span><span class="sxs-lookup"><span data-stu-id="bdb18-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bdb18-137">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="bdb18-137">Next steps</span></span>

<span data-ttu-id="bdb18-138">Bygg på toppen av de supplerte kundedataene.</span><span class="sxs-lookup"><span data-stu-id="bdb18-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bdb18-139">Opprett [segmenter](segments.md) og [mål](measures.md), og [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.</span><span class="sxs-lookup"><span data-stu-id="bdb18-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]