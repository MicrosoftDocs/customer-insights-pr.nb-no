---
title: Eksporter data til Azure Synapse Analytics (forhåndsversjon)
description: Finn ut hvordan du konfigurerer tilkoblingen til Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196406"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Eksporter data til Azure Synapse Analytics (forhåndsversjon)

Azure Synapse er en analysetjeneste som akselererer tid til innsikt på tvers av datalagre og store datasystemer. Du kan ta inn og bruke Customer Insights-dataene i [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Forutsetning

> [!NOTE]
> Pass på at du angir alle **rolletilordninger** slik det er beskrevet.

- I Customer Insights må Azure Active Directory-brukerkontoen (AD) ha en [administratorrolle](permissions.md#assign-roles-and-permissions).

I Azure:

- Et aktivt Azure-abonnement.

- Hvis du bruker en ny Azure Data Lake Storage Gen2-konto, har [tjenestekontohaveren for Customer Insights](connect-service-principal.md) sikkerhetstillatelsene **Storage Blob-databidragsyter**. Data Lake Storage Gen2 **må ha** [hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace) aktivert.

- I ressursgruppen der Azure Synapse workspace er plassert, må *tjenestekontohaveren* og *Azure AD-brukeren med administratortillatelser i Customer Insights* minst få tilordnet **Leser**-[tillatelser](/azure/role-based-access-control/role-assignments-portal).

- *Azure AD-brukeren med administratortillatelser i Customer Insights* har tillatelsene **Storage Blob-databidragsyter** på  Azure Data Lake Storage Gen2-kontoen der dataene er plassert og koblet til Azure Synapse workspace. Finn ut mer om hvordan du [bruker Azure Portal til å tilordne en Azure-rolle for tilgang til blob- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [tillatelsene for Storage Blob-databidragsyter](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse workspace-administrert identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* har tillatelsene **Storage Blob-databidragsyter** på Azure Data Lake Storage Gen2-kontoen der dataene er plassert og koblet til Azure Synapse workspace. Finn ut mer om hvordan du [bruker Azure Portal til å tilordne en Azure-rolle for tilgang til blob- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [tillatelsene for Storage Blob-databidragsyter](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- I Azure Synapse workspace har *tjenestekontohaveren for Customer Insights* følgende [rolle tilordnet](/azure/synapse-analytics/security/how-to-set-up-access-control): **Synapse-administrator**.

## <a name="set-up-connection-to-azure-synapse"></a>Konfigurer tilkoblingen til Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Azure Synapse Analytics**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg eller søk etter abonnementet du vil bruke Customer Insights-dataene i. Så snart et abonnement er valgt, kan du også velge **Arbeidsområde**, **Lagringskonto** og **Beholder**.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)] Hvis du vil konfigurere eksporten med en delt tilkobling, må du minst ha **Bidragsyter**-tillatelser i Customer Insights.

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra delen Azure Synapse Analytics i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Angi et gjenkjennelig **visningsnavn** for eksporten og et **databasenavn**. Eksporten oppretter en ny [Azure Synapse-sjødatabase](/azure/synapse-analytics/database-designer/concepts-lake-database) i arbeidsområdet som er definert i tilkoblingen.

1. Velg hvilke enheter du vil eksportere til Azure Synapse Analytics.
   > [!NOTE]
   > Datakilder som er basert på en [Common Data Model-mappe](connect-common-data-model.md), støttes ikke.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Hvis du vil spørre etter data som ble eksportert til Synapse Analytics, trenger du tilgangen **Leser for Storage Blob Data** til mållageret i arbeidsområdet for eksporter.

## <a name="update-an-export"></a>Oppdater en eksport

1. Gå til **Data** > **Eksporter**.

1. Velg **Rediger** på eksporten du vil oppdatere.

   - **Legg til** eller **Fjern** enheter fra utvalget. Hvis enheter fjernes fra utvalget, slettes de ikke fra Synapse Analytics-databasen. Fremtidige data oppdateres imidlertid ikke for de fjernede enhetene i databasen.

   - **Endring av databasenavnet** oppretter en ny Synapse Analytics-database. Databasen med navnet som ble konfigurert før, vil ikke motta oppdateringer i fremtidige oppdateringer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
