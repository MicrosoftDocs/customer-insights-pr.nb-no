---
title: Supplering med egendefinert SFTP-import
description: Generell informasjon om supplering med egendefinert SFTP-import.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304662"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="1c46c-103">Supplere kundeprofiler med egendefinerte data (forhåndsversjon)</span><span class="sxs-lookup"><span data-stu-id="1c46c-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="1c46c-104">Med egendefinert SFTP-import (Secure File Transfer Protocol) kan du importere data som ikke trenger å gå gjennom dataforening.</span><span class="sxs-lookup"><span data-stu-id="1c46c-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="1c46c-105">Det er en fleksibel, sikker og enkel måte å skaffe seg på dataene på.</span><span class="sxs-lookup"><span data-stu-id="1c46c-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="1c46c-106">Egendefinert SFTP-import kan brukes i kombinasjon med [SFTP-eksport](export-sftp.md), noe som gjør at du kan eskportere kundeprofildataene som er nødvendig for supplering.</span><span class="sxs-lookup"><span data-stu-id="1c46c-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="1c46c-107">Dataene kan deretter behandles og suppleres, og tilpasset SFTP-import kan brukes for å hente de supplerte dataene tilbake til målgruppeinnsiktsmulighetene i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1c46c-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1c46c-108">Forutsetninger</span><span class="sxs-lookup"><span data-stu-id="1c46c-108">Prerequisites</span></span>

<span data-ttu-id="1c46c-109">For å konfigure egendefinert SFTP-import må følgende forhåndskrav være oppfylt:</span><span class="sxs-lookup"><span data-stu-id="1c46c-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="1c46c-110">Du har filnavnet og plasseringen (banen) til filen som skal importeres til SFTP-verten.</span><span class="sxs-lookup"><span data-stu-id="1c46c-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="1c46c-111">Det finnes en *model.json*-fil som angir [Common Data Model-skjemaet](/common-data-model/) for dataene som skal importeres.</span><span class="sxs-lookup"><span data-stu-id="1c46c-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="1c46c-112">Denne filen må være i samme katalog som filen som skal importeres.</span><span class="sxs-lookup"><span data-stu-id="1c46c-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="1c46c-113">En SFTP-tilkobling er allerede konfigurert av en *administrator*, eller du har [administrator](permissions.md#administrator)-tillatelser.</span><span class="sxs-lookup"><span data-stu-id="1c46c-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="1c46c-114">Du trenger legitimasjonen for brukeren, URL-adressen og portnummeret for SFTP-plasseringen der du vil importere data fra.</span><span class="sxs-lookup"><span data-stu-id="1c46c-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="1c46c-115">Konfigurer importen</span><span class="sxs-lookup"><span data-stu-id="1c46c-115">Configure the import</span></span>

1. <span data-ttu-id="1c46c-116">Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.</span><span class="sxs-lookup"><span data-stu-id="1c46c-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="1c46c-117">På **flisen for egendefinert SFTP-import** velger du **Suppler dataene** og deretter **Kom i gang**.</span><span class="sxs-lookup"><span data-stu-id="1c46c-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Flis for egendefinert SFTP-import.":::

1. <span data-ttu-id="1c46c-119">Velg en [tilkobling](connections.md) fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="1c46c-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="1c46c-120">Kontakt en administrator hvis ingen tilkobling er tilgjengelig.</span><span class="sxs-lookup"><span data-stu-id="1c46c-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="1c46c-121">Hvis du er en administrator, kan du opprette en tilkobling ved å velge **Legg til tilkobling** og velge **tilpasset SFTP-import** fra rullegardinlisten.</span><span class="sxs-lookup"><span data-stu-id="1c46c-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="1c46c-122">Velg **Koble til egendefinert import** for å bekrefte valget av tilkobling.</span><span class="sxs-lookup"><span data-stu-id="1c46c-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="1c46c-123">Velg **Neste**, og angi **Bane** og **Filnavn** for datafilen du vil importere.</span><span class="sxs-lookup"><span data-stu-id="1c46c-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Skjermbilde når du angir dataplassering.":::

1. <span data-ttu-id="1c46c-125">Velg **Neste** angi et navn for suppleringen og et navn for utdataenheten.</span><span class="sxs-lookup"><span data-stu-id="1c46c-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="1c46c-126">Velg **Lagre supplering** etter at du har sett gjennom valgene.</span><span class="sxs-lookup"><span data-stu-id="1c46c-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="1c46c-127">Konfigurere tilkoblingen for egendefinert import av SFTP</span><span class="sxs-lookup"><span data-stu-id="1c46c-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="1c46c-128">Du må være en administrator for å konfigurere tilkoblinger.</span><span class="sxs-lookup"><span data-stu-id="1c46c-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="1c46c-129">Velg **Legg til tilkobling** når du konfigurerer en supplering *eller* gå til **Administrasjon** > **Tilkoblinger** og velg **Konfigurer** i Egendefinert import-flisen.</span><span class="sxs-lookup"><span data-stu-id="1c46c-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="1c46c-130">Skriv inn et navn på tilkoblingen i **Visningsnavn**-boksen.</span><span class="sxs-lookup"><span data-stu-id="1c46c-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="1c46c-131">Angi et gyldig brukernavn, passord og verts-URL for SFTP-serveren som dataene som skal importeres, finnes på.</span><span class="sxs-lookup"><span data-stu-id="1c46c-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="1c46c-132">Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**.</span><span class="sxs-lookup"><span data-stu-id="1c46c-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="1c46c-133">Velg **Bekreft** for å validere konfigurasjonen.</span><span class="sxs-lookup"><span data-stu-id="1c46c-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="1c46c-134">Når verifiseringen er fullført, kan tilkoblingen lagres ved å velge **Lagre**.</span><span class="sxs-lookup"><span data-stu-id="1c46c-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1c46c-135">![Experian-tilkoblingskonfigurasjonsside](media/enrichment-SFTP-connection.png "Experian-tilkoblingskonfigurasjonsside")</span><span class="sxs-lookup"><span data-stu-id="1c46c-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="1c46c-136">Definere felttilordninger</span><span class="sxs-lookup"><span data-stu-id="1c46c-136">Defining field mappings</span></span> 

<span data-ttu-id="1c46c-137">Katalogen som inneholder filen som skal importeres på SFTP-serveren, må også inneholde en *model.json*-fil.</span><span class="sxs-lookup"><span data-stu-id="1c46c-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="1c46c-138">Denne filen definerer skjemaet som skal brukes til å importere dataene.</span><span class="sxs-lookup"><span data-stu-id="1c46c-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="1c46c-139">Skjemaet må bruke [Common Data Model](/common-data-model/) for å angi felttilordningen.</span><span class="sxs-lookup"><span data-stu-id="1c46c-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="1c46c-140">Et enkelt eksempel på en model.json-fil ser slik ut:</span><span class="sxs-lookup"><span data-stu-id="1c46c-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="1c46c-141">Resultater av supplering</span><span class="sxs-lookup"><span data-stu-id="1c46c-141">Enrichment results</span></span>

<span data-ttu-id="1c46c-142">Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="1c46c-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="1c46c-143">Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1c46c-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1c46c-144">Behandlingstiden avhenger av størrelsen på dataene som skal importeres, og tilkoblingen til SFTP-serveren.</span><span class="sxs-lookup"><span data-stu-id="1c46c-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="1c46c-145">Når suppleringsprosessen er fullført, kan du se gjennom de nylig importerte egendefinerte suppleringsdataene under **Mine suppleringer**.</span><span class="sxs-lookup"><span data-stu-id="1c46c-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="1c46c-146">I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.</span><span class="sxs-lookup"><span data-stu-id="1c46c-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="1c46c-147">Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.</span><span class="sxs-lookup"><span data-stu-id="1c46c-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1c46c-148">Neste trinn</span><span class="sxs-lookup"><span data-stu-id="1c46c-148">Next steps</span></span>

<span data-ttu-id="1c46c-149">Bygg på toppen av de supplerte kundedataene.</span><span class="sxs-lookup"><span data-stu-id="1c46c-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="1c46c-150">Opprett [segmenter](segments.md) og [mål](measures.md), og [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.</span><span class="sxs-lookup"><span data-stu-id="1c46c-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
