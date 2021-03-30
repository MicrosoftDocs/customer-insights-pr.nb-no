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
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Bruk Customer Insights-segmenter i Adobe Campaign Standard (forhåndsversjon)

Som bruker av målgruppeinnsikt for Dynamics 365 Customer Insights har du kanskje opprettet segmenter for å gjøre markedsføringskampanjene mer effektive ved å rette deg mot relevante målgrupper. Hvis du vil bruke et segment fra målgruppeinnsikt i Adobe Experience Platform og programmer som Adobe Campaign Standard, må du følge noen få trinn som er beskrevet i denne artikkelen.

:::image type="content" source="media/ACS-flow.png" alt-text="Prosessdiagram for trinnene beskrevet i denne artikkelen.":::

## <a name="prerequisites"></a>Forutsetninger

-   Dynamics 365 Customer Insights-lisens
-   Adobe Campaign Standard-lisens
-   Azure Blob Storage-konto

## <a name="campaign-overview"></a>Kampanjeoversikt

For en bedre forståelse av hvordan du kan bruke segmenter fra målgruppeinnsikt i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampanje.

La oss anta at firmaet ditt tilbyr en månedlig abonnementsbasert tjeneste til kundene i USA. Du ønsker å identifisere kunder som har abonnementer som skal fornyes i løpet av de neste åtte dagene, men som ennå ikke har fornyet abonnementet. Hvis du vil beholde disse kundene, må du sende dem et kampanjetilbud via e-post ved hjelp av Adobe Campaign Standard.

I dette eksemplet skal vi kjøre den promoterende e-postkampanjen én gang. Denne artikkelen dekker ikke brukstilfellet for kjøring av kampanjen flere ganger. Målgruppeinnsikt og Adobe Campaign Standard kan imidlertid konfigureres til også å fungere for et gjentakende kampanjescenario.

## <a name="identify-your-target-audience"></a>Identifiser målgruppen

I vårt scenario antar vi at e-postadressene til kundene er tilgjengelige i målgruppeinnsikt, og at kampanjepreferansene deres ble analysert for å identifisere medlemmer i segmentet.

[Segmentet du definerte i målgruppeinnsikt](segments.md), kalles **ChurnProneCustomers**, og du planlegger å sende e-postkampanjen til disse kundene.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skjermbilde av segmentsiden med ChurnProneCustomers -segmentet opprettet.":::

E-postmeldingen for tilbudet du vil sende ut, inneholder kundens fornavn, etternavn og sluttdatoen for abonnementet. Den informerer kundene om rabatten de får hvis de fornyer abonnementet før abonnementet avsluttes.

## <a name="export-your-target-audience"></a>Eksporter målgruppen

Når målgruppen er identifisert, kan vi konfigurere eksporten fra målgruppeinnsikt til en Azure Blob Storage-konto.

1. I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.

1. I flisen **Adobe-kampanje** velger du **Oppsett**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurasjonsflis for Adobe Campaign Standard.":::

1. Angi et **visningsnavn** for dette nye eksportmålet, og angi deretter **kontonavnet**, **kontonøkkelen** og **beholderen** for Azure Blob Storage-kontoen du vil eksportere segmentet til.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skjermbilde av konfigurasjonen av lagringskontoen. "::: 

   - Hvis du vil vite mer om hvordan du finner navnet og nøkkelen til Azure Blob Storage-kontoen, kan du se [Administrere lagringskontoinnstillinger i Azure-portalen](/azure/storage/common/storage-account-manage).

   - Hvis du vil lære hvordan du oppretter en beholder, kan du se [Opprette en beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Velg **Neste**.

1. Velg segmentet du vil eksportere. I dette eksemplet er det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skjermbilde av brukergrensesnittet for segmentvalg med ChurnProneCustomers-segmentet valgt.":::

1. Velg **Neste**.

1. Nå tilordner vi **Kilde**-feltene fra målgruppeinnsiktssegmentet til **Mål**-feltnavnene i Adobe Campaign Standard-profilskjemaet.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Felttilordning for Adobe Campaign Standard-koblingen.":::

   Hvis du vil legge til flere attributter, velger du **Legg til attributt**. Målnavnet kan være et annet enn kildefeltnavnet, slik at du fremdeles kan tilordne segmentutdata fra målgruppeinnsikt til Adobe Campaign Standard hvis feltene ikke har samme navn i de to systemene.

   > [!NOTE]
   > E-postadressen brukes som et identitetsfelt, men du kan bruke alle andre identifikatorer fra målgruppeinnsikt til å tilordne data til Adobe Campaign Standard.

1. Velg **Lagre**.

Når du har lagret eksportmålet, finner du det i **Administrator** > **Eksporter** > **Mine eksportmål**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Skjermbilde med listen over eksporter og eksempelsegment uthevet.":::

Du kan nå [eksportere segmentet ved behov](export-destinations.md#export-data-on-demand). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md).

> [!NOTE]
> Kontroller at antall oppføringer i det eksporterte segmentet er innenfor den tillatte grensen for Adobe Campaign Standard-lisensen.

Eksporterte data lagres i Azure Blob Storage-beholderen du konfigurerte ovenfor. Følgende mappebane opprettes automatisk i beholderen:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurer Adobe Campaign Standard

Når et segment fra målgruppeinnsikt eksporteres, inneholder det kolonnene du valgte da du definerte eksportmålet i forrige trinn. Disse dataene kan brukes til å [opprette profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Hvis du vil bruke segmentet i Adobe Campaign Standard, må vi utvide profilskjemaet i Adobe Campaign Standard til å inkludere to tilleggsfelter. Lær hvordan du [utvider profilressursen](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) med nye felt i Adobe Campaign Standard.

I vårt eksempel er disse feltene *Segmentnavn og Segmentdato (valgfritt).*

Vi skal bruke disse feltene til å identifisere profilene i Adobe Campaign Standard som vi vil målrette for denne kampanjen.

Hvis det ikke finnes andre oppføringer i Adobe Campaign Standard enn den du skal importere, kan du hoppe over dette trinnet.

## <a name="import-data-into-adobe-campaign-standard"></a>Importer data til Adobe Campaign Standard

Nå som alt er klart, må vi importere de klargjorte målgruppedataene fra målgruppeinnsikt til Adobe Campaign Standard for å opprette profiler. Lær [hvordan du importerer profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) ved hjelp av en arbeidsflyt.

Importarbeidsflyten i bildet nedenfor er konfigurert til å kjøre hver 8. time og ser etter eksporterte målgruppeinnsiktssegmenter (CSV-fil i Azure Blob Storage). Arbeidsflyten pakker ut CSV-filinnholdet i en bestemt kolonnerekkefølge. Denne arbeidsflyten er bygget for å utføre grunnleggende feilhåndtering og sikre at hver oppføring har en e-postadresse før dataene samles inn i Adobe Campaign Standard. Arbeidsflyten pakker også ut segmentnavnet fra filnavnet før det blir satt opp i ACS-profildata.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Skjermbilde av en importarbeidsflyt i brukergrensesnittet til Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Hent målgruppen i Adobe Campaign Standard

Når dataene er importert til Adobe Campaign Standard, kan du [opprette en arbeidsflyt](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) og [spørre](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) kundene basert på *Segmentnavn* og *Segmentdato* for å velge profiler som ble identifisert for eksempelkampanjen vår.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Opprett og send e-posten ved hjelp av Adobe Campaign Standard

Opprett e-postinnholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-posten din.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på e-post med fornyelsestilbud fra Adobe Campaign Standard.":::