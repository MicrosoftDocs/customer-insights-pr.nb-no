---
title: Eksporter segmenter til Adobe Experience Platform (forhåndsversjon)
description: Finn ut hvordan du bruker Customer Insights-segmenter i Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052523"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Eksporter segmenter til Adobe Experience Platform (forhåndsversjon)

Som en bruker av Dynamics 365 Customer Insights har du kanskje opprettet segmenter for å gjøre markedsføringskampanjene mer effektive ved å rette deg mot relevante målgrupper. Hvis du vil bruke et segment fra Customer Insights i Adobe Experience Platform og programmer som Adobe Campaign Standard, må du følge noen få trinn som er beskrevet i denne artikkelen.

:::image type="content" source="media/AEP-flow.png" alt-text="Prosessdiagram for trinnene beskrevet i denne artikkelen.":::

## <a name="prerequisites"></a>Forutsetninger

-   Dynamics 365 Customer Insights-lisens
-   Adobe Experience Platform-lisens
-   Adobe Campaign Standard-lisens
-   Azure Blob Storage-konto

## <a name="campaign-overview"></a>Kampanjeoversikt

For å bedre forstå hvordan du kan bruke segmenter fra Customer Insights i Adobe Experience Platform kan vi se på en fiktiv eksempelkampanje.

La oss anta at firmaet ditt tilbyr en månedlig abonnementsbasert tjeneste til kundene i USA. Du ønsker å identifisere kunder som har abonnementer som skal fornyes i løpet av de neste åtte dagene, men som ennå ikke har fornyet abonnementet. Hvis du vil beholde disse kundene, vil du sende dem et kampanjetilbud via e-post ved hjelp av Adobe Experience Platform.

I dette eksemplet skal vi kjøre den promoterende e-postkampanjen én gang. Denne artikkelen dekker ikke brukstilfellet for kjøring av kampanjen flere ganger.

## <a name="identify-your-target-audience"></a>Identifiser målgruppen

I vårt scenario antar vi at e-postadressene til kundene er tilgjengelige i Customer Insights, og at kampanjeinnstillingene er analysert for å identifisere medlemmer i segmentet.

[Segmentet du definerte i Customer Insights](segments.md), kalles **ChurnProneCustomers**, og du planlegger å sende disse kundene e-postkampanjen.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skjermbilde av segmentsiden med ChurnProneCustomers -segmentet opprettet.":::

E-postmeldingen for tilbudet du vil sende ut, inneholder kundens fornavn, etternavn og sluttdatoen for abonnementet. Den informerer kundene om rabatten de får hvis de fornyer abonnementet før abonnementet avsluttes.

## <a name="export-your-target-audience"></a>Eksporter målgruppen

Når målgruppen er identifisert, kan vi konfigurere eksporten fra Customer Insights til en Azure Blob Storage-konto.

### <a name="configure-a-connection"></a>Konfigurer en tilkobling

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Azure Blob-lagring**, eller velg **Konfigurer** på **Azure Blob-lagring**-flisen for å konfigurere tilkoblingen.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurasjon-flis for Azure Blob Storage."::: 

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **Kontonavn:**, **Kontonøkkel** og **Beholder** for Blob Storage-kontoen du vil eksportere segmentet til.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skjermbilde av konfigurasjonen av lagringskontoen. "::: 
   
    - Hvis du vil finne ut mer om hvordan du finner navn på forretningsforbindelse og kontonøkkel for Blob Storage, kan du se [Behandle innstillinger for lagringskonto i Azure Portal](/azure/storage/common/storage-account-manage).
    - Hvis du vil lære hvordan du oppretter en beholder, kan du se [Opprette en beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Velg **Lagre** for å fullføre tilkoblingen. 

### <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport** for å opprette en ny eksport.

1. Velg en tilkobling fra Azure Blob Storage-delen i feltet **Tilkobling for eksport**. Hvis navnet på denne delen ikke vises, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Velg segmentet du vil eksportere. I dette eksemplet er det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skjermbilde av brukergrensesnittet for segmentvalg med ChurnProneCustomers-segmentet valgt.":::

1. Velg **Lagre**.

Når du har lagret eksportmålet, finner du det i **Data** > **Eksporter**.

Du kan nå [eksportere segmentet ved behov](export-destinations.md#run-exports-on-demand). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md).

> [!NOTE]
> Kontroller at antall oppføringer i det eksporterte segmentet er innenfor den tillatte grensen for Adobe Campaign Standard-lisensen.

Eksporterte data lagres i Azure Blob Storage-beholderen du konfigurerte ovenfor. Følgende mappebane opprettes automatisk i beholderen:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* for de eksporterte enhetene er på *%ExportDestinationName%*-nivået.

Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definer opplevelsesdatamodell (XDM) i Adobe Experience Platform

Før de eksporterte dataene fra Customer Insights kan brukes i Adobe Experience Platform, må vi definere skjemaet for opplevelsesdatamodell og [konfigurere dataene for kundeprofilen i sanntid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Finn ut [hva XDM er](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) og forstå det [grunnleggende innen skjemakomposisjon](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importere data til Adobe Experience Platform

Nå som alt er på plass, må vi importere de forberedte målgruppedataene fra Customer Insights til Adobe Experience Platform.

Først må du [opprette en Azure Blob Storage-kildetilkobling](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Når du har definert kildetilkoblingen, [konfigurerer du en dataflyt](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for en gruppetilkobling for skylagring for å importere segmentutdataene fra Customer Insights til Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Opprett en målgruppe i Adobe Campaign Standard

Hvis du vil sende e-posten for denne kampanjen, bruker vi Adobe Campaign Standard. Etter importen av dataene til Adobe Experience Platform, må vi [opprette en målgruppe](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard ved hjelp av dataene i Adobe Experience Platform.


Lær hvordan du [bruker segmentverktøyet](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) i Adobe Campaign Standard til å definere en målgruppe basert på dataene i Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Opprett og send e-posten ved hjelp av Adobe Campaign Standard

Opprett e-postinnholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-posten din.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på e-post med fornyelsestilbud fra Adobe Campaign Standard.":::
