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
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Bruk Customer Insights-segmenter i Adobe Experience Platform (forhåndsversjon)

Som bruker av målgruppeinnsikt for Dynamics 365 Customer Insights har du kanskje opprettet segmenter for å gjøre markedsføringskampanjene mer effektive ved å rette deg mot relevante målgrupper. Hvis du vil bruke et segment fra målgruppeinnsikt i Adobe Experience Platform og programmer som Adobe Campaign Standard, må du følge noen få trinn som er beskrevet i denne artikkelen.

:::image type="content" source="media/AEP-flow.png" alt-text="Prosessdiagram for trinnene beskrevet i denne artikkelen.":::

## <a name="prerequisites"></a>Forutsetninger

-   Dynamics 365 Customer Insights-lisens
-   Adobe Experience Platform-lisens
-   Adobe Campaign Standard-lisens
-   Azure Blob Storage-konto

## <a name="campaign-overview"></a>Kampanjeoversikt

For en bedre forståelse av hvordan du kan bruke segmenter fra målgruppeinnsikt i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampanje.

La oss anta at firmaet ditt tilbyr en månedlig abonnementsbasert tjeneste til kundene i USA. Du ønsker å identifisere kunder som har abonnementer som skal fornyes i løpet av de neste åtte dagene, men som ennå ikke har fornyet abonnementet. Hvis du vil beholde disse kundene, må du sende dem et kampanjetilbud via e-post ved hjelp av Adobe Experience Platform.

I dette eksemplet skal vi kjøre den promoterende e-postkampanjen én gang. Denne artikkelen dekker ikke brukstilfellet for kjøring av kampanjen flere ganger.

## <a name="identify-your-target-audience"></a>Identifiser målgruppen

I vårt scenario antar vi at e-postadressene til kundene er tilgjengelige i målgruppeinnsikt, og at kampanjepreferansene deres ble analysert for å identifisere medlemmer i segmentet.

[Segmentet du definerte i målgruppeinnsikt](segments.md), kalles **ChurnProneCustomers**, og du planlegger å sende e-postkampanjen til disse kundene.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skjermbilde av segmentsiden med ChurnProneCustomers -segmentet opprettet.":::

E-postmeldingen for tilbudet du vil sende ut, inneholder kundens fornavn, etternavn og sluttdatoen for abonnementet. Den informerer kundene om rabatten de får hvis de fornyer abonnementet før abonnementet avsluttes.

## <a name="export-your-target-audience"></a>Eksporter målgruppen

Når målgruppen er identifisert, kan vi konfigurere eksporten fra målgruppeinnsikt til en Azure Blob Storage-konto.

1. I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.

1. På flisen **Azure Blob Storage** velger du **Konfigurer**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurasjon-flis for Azure Blob Storage.":::

1. Angi et **visningsnavn** for dette nye eksportmålet, og angi deretter **kontonavnet**, **kontonøkkelen** og **beholderen** for Azure Blob Storage-kontoen du vil eksportere segmentet til.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skjermbilde av konfigurasjonen av lagringskontoen. "::: 

   - Hvis du vil vite mer om hvordan du finner navnet og nøkkelen til Azure Blob Storage-kontoen, kan du se [Administrere lagringskontoinnstillinger i Azure-portalen](/azure/storage/common/storage-account-manage).

   - Hvis du vil lære hvordan du oppretter en beholder, kan du se [Opprette en beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Velg **Neste**.

1. Velg segmentet du vil eksportere. I dette eksemplet er det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skjermbilde av brukergrensesnittet for segmentvalg med ChurnProneCustomers-segmentet valgt.":::

1. Velg **Lagre**.

Når du har lagret eksportmålet, finner du det i **Administrator** > **Eksporter** > **Mine eksportmål**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Skjermbilde med listen over eksporter og eksempelsegment uthevet.":::

Du kan nå [eksportere segmentet ved behov](export-destinations.md#export-data-on-demand). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md).

> [!NOTE]
> Kontroller at antall oppføringer i det eksporterte segmentet er innenfor den tillatte grensen for Adobe Campaign Standard-lisensen.

Eksporterte data lagres i Azure Blob Storage-beholderen du konfigurerte ovenfor. Følgende mappebane opprettes automatisk i beholderen:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* for de eksporterte enhetene er på *%ExportDestinationName%*-nivået.

Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definer Experience Data Model (XDM) i Adobe Experience Platform

Før de eksporterte dataene fra målgruppeinnsikt kan brukes i Adobe Experience Platform, må vi definere Experience Data Model-skjemaet og [konfigurere dataene for kundeprofilen i sanntid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Finn ut [hva XDM er](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) og forstå det [grunnleggende innen skjemakomposisjon](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importer data til Adobe Experience Platform

Nå som alt er klart, må vi importere de klargjorte målgruppedataene fra målgruppeinnsikt til Adobe Experience Platform.

Først må du [opprette en Azure Blob Storage-kildetilkobling](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Når du har definert kildetilkoblingen, må du [konfigurere en dataflyt](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for en skylagringstilkobling for å importere segmentutdataene fra målgruppeinnsikt til Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Opprett en målgruppe i Adobe Campaign Standard

Til å sende e-posten for denne kampanjen bruker vi Adobe Campaign Standard. Når du har importert dataene til Adobe Experience Platform, må vi [opprette en målgruppe](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard ved å bruke dataene i Adobe Experience Platform.

Lær hvordan du [bruker segmentverktøyet](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) i Adobe Campaign Standard til å definere en målgruppe basert på dataene i Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Opprett og send e-posten ved hjelp av Adobe Campaign Standard

Opprett e-postinnholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-posten din.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på e-post med fornyelsestilbud fra Adobe Campaign Standard.":::