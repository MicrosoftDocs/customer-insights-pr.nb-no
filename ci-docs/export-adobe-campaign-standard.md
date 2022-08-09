---
title: Eksporter Customer Insights-segmenter til Adobe Campaign Standard (forhåndsversjon)
description: Finn ut hvordan du bruker Customer Insights-segmenter i Adobe Campaign Standard.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195532"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Eksporter Customer Insights-segmenter til Adobe Campaign Standard (forhåndsversjon)

Eksporter segmenter som er rettet mot relevante målgrupper, til Adobe Campaign Standard.

:::image type="content" source="media/ACS-flow.png" alt-text="Prosessdiagram for trinnene beskrevet i denne artikkelen.":::

## <a name="prerequisites"></a>Forutsetning

- En Adobe Campaign Standard-lisens.
- Et navn og en kontonøkkel for [Azure Blob Storage-konto](/azure/storage/blobs/create-data-lake-storage-account). Du finner navnet og nøkkelen ved å se [Administrer lagringskontoinnstillinger i Azure Portal](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage-beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Kampanjeoversikt

For å bedre forstå hvordan du kan bruke segmenter fra Customer Insights i Adobe Experience Platform kan vi se på en fiktiv eksempelkampanje.

La oss anta at firmaet ditt tilbyr en månedlig abonnementsbasert tjeneste til kundene i USA. Du ønsker å identifisere kunder som har abonnementer som skal fornyes i løpet av de neste åtte dagene, men som ennå ikke har fornyet abonnementet. Hvis du vil beholde disse kundene, vil du sende dem et kampanjetilbud via e-post ved hjelp av Adobe Campaign Standard.

I dette eksemplet skal vi kjøre den promoterende e-postkampanjen én gang. Denne artikkelen dekker ikke brukstilfellet for kjøring av kampanjen flere ganger. Customer Insights og Adobe Campaign Standard kan imidlertid konfigureres til å fungere for et regelmessig kampanjescenario også.

## <a name="identify-your-target-audience"></a>Identifiser målgruppen

I vårt scenario antar vi at e-postadressene til kundene er tilgjengelige i Customer Insights, og at kampanjeinnstillingene er analysert for å identifisere medlemmer i segmentet.

[Segmentet du definerte i Customer Insights](segments.md), kalles **ChurnProneCustomers**, og du planlegger å sende disse kundene e-postkampanjen.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skjermbilde av segmentsiden med ChurnProneCustomers -segmentet opprettet.":::

E-postmeldingen for tilbudet du vil sende ut, inneholder kundens fornavn, etternavn og sluttdatoen for abonnementet. Den informerer kundene om rabatten de får hvis de fornyer abonnementet før abonnementet avsluttes.

## <a name="export-your-target-audience"></a>Eksporter målgruppen

### <a name="set-up-connection-to-adobe-campaign"></a>Konfigurer tilkoblingen til Adobe Campaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling** og velg **Adobe Campaign**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **Kontonavn**, **Kontonøkkel** og **Beholder** for Blob Storage-kontoen.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skjermbilde av konfigurasjonen av lagringskontoen. ":::

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

### <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg feltet **Tilkobling for eksport**, og velg en tilkobling fra Adobe Campaign-delen. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg segmentet du vil eksportere. I dette eksemplet er det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skjermbilde av brukergrensesnittet for segmentvalg med ChurnProneCustomers-segmentet valgt.":::

1. Velg **Neste**.

1. Tilordne **Kilde**-feltene fra Customer Insights-segmentet til **Mål**-feltnavnene i Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Felttilordning for Adobe Campaign Standard-tilkobling.":::

   Hvis du vil legge til flere attributter, velger du **Legg til attributt**. Målnavnet kan være et annet enn for kildefeltnavnet slik at du fremdeles kan tildele segmentutdata fra Customer Insights til Adobe Campaign Standard hvis feltene ikke har samme navn i de to systemene.

   > [!NOTE]
   > E-postadressen brukes som et identitetsfelt, men du kan bruke alle andre identifikatorer fra kundeprofilen til å tildele data til Adobe Campaign Standard.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Kontroller at antall oppføringer i det eksporterte segmentet er innenfor den tillatte grensen for Adobe Campaign Standard-lisensen.

Eksporterte data lagres i Azure Blob Storage-beholderen du konfigurerte ovenfor. Følgende mappebane opprettes automatisk i beholderen: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurer Adobe Campaign Standard

Eksporterte segmenter inneholder kolonnene du valgte mens du konfigurerte eksporten. Disse dataene kan brukes til å [opprette profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Hvis du vil bruke segmentet i Adobe Campaign Standard, må du [utvide profilskjemaet](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) i Adobe Campaign Standard for å ta med to tilleggsfelter.

I vårt eksempel er disse feltene Segmentnavn og Segmentdato. Vi skal bruke disse feltene til å identifisere profilene i Adobe Campaign Standard som vi vil rette oss mot for denne kampanjen.

Hvis det ikke finnes andre oppføringer i Adobe Campaign Standard enn de du skal importere, hopper du over dette trinnet.

## <a name="import-data-into-adobe-campaign-standard"></a>Importer data til Adobe Campaign Standard

Importer de forberedte målgruppedataene fra Customer Insights til Adobe Campaign Standard for å [opprette profiler ved hjelp av en arbeidsflyt](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)

Importarbeidsflyten på bildet nedenfor er konfigurert til å kjøre hver åttende time og ser etter eksporterte Customer Insights-segmenter (CSV-fil i Azure Blob Storage). Arbeidsflyten pakker ut CSV-filinnholdet i en bestemt kolonnerekkefølge. Denne arbeidsflyten er bygget for å utføre grunnleggende feilhåndtering og sikre at hver oppføring har en e-postadresse før dataene samles i Adobe Campaign Standard. Arbeidsflyten pakker også ut segmentnavnet fra filnavnet før oppdatering til Adobe Campaign Standard-profildataene.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Skjermbilde av en importarbeidsflyt i Adobe Campaign Standard-brukergrensesnittet.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Hent målgruppen i Adobe Campaign Standard

Når dataene er importert til Adobe Campaign Standard, kan du [opprette en arbeidsflyt](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) og [spørre](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) kundene basert på segmentnavnet og segmentdatoen for å velge profiler som ble identifisert for eksempelkampanjen.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Opprett og send e-posten ved hjelp av Adobe Campaign Standard

Opprett e-postinnholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-posten din.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på e-post med fornyelsestilbud fra Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
