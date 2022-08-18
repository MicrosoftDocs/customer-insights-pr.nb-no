---
title: Koble til en Azure Synapse-datakilde (forhåndsversjon)
description: Bruk en database i Azure Synapse som en datakilde i Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259810"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Koble til en Azure Synapse Analytics-datakilde (forhåndsversjon)

Azure Synapse Analytics er en bedriftsanalysetjeneste som akselererer tid til innsikt på tvers av datalagre og stordatasystemer. Azure Synapse Analytics samler sammen det beste av SQL-teknologi som brukes i bedriftsdatalagring, Spark-teknologier som brukes til stordata, Data Explorer for analyse av logg- og tidsserier, forløp for dataintegrering og ETL/ELT samt grundig integrasjon med andre Azure-tjenester som Power BI, Cosmos DB og AzureML.

Hvis du vil ha mer informasjon, kan du se [Oversikt over Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Forutsetning

> [!NOTE]
> Synapse Workspaces som har [brannmuraktivert](/azure/synapse-analytics/security/synapse-workspace-ip-firewall), støttes for øyeblikket ikke.
> [!IMPORTANT]
> Pass på at du angir alle **rolletilordninger** slik det er beskrevet.  

**I Customer Insights**:

* Du har en **administratorrolle** i Customer Insights. Finn ut mer om [brukertillatelser i Customer Insights](permissions.md#add-users).

**I Azure**:

- Et aktivt Azure-abonnement.

- Hvis du bruker en ny Azure Data Lake Storage Gen2-konto, må *tjenestekontohaveren for Customer Insights* som er Dynamics 365 AI for Customer Insights, ha sikkerhetstillatelsene **Storage Blob-databidragsyter**. Finn ut mer om hvordan du [kobler en Azure Data Lake Storage sammen med en tjenestekontohaver for Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **må ha** [hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace) aktivert.

- På ressursgruppen der Azure Synapse workspace er plassert, må *tjenestekontohaveren* som er Dynamics 365 AI for Customer Insights, og *brukeren for Customer Insights* må være tildelt minst **Leser**-tillatelser. Hvis du vil ha mer informasjon, kan du se [Tilordne Azure-roller ved hjelp av Azure Portal](/azure/role-based-access-control/role-assignments-portal).

- *Brukeren* må ha tillatelsene **Storage Blob-databidragsyter** på Azure Data Lake Storage Gen2-kontoen der dataene er plassert og koblet til Azure Synapse-arbeidsområdet. Finn ut mer om hvordan du [bruker Azure Portal til å tilordne en Azure-rolle for tilgang til blob- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [tillatelsene for Storage Blob-databidragsyter](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse-arbeidsområdeadministrert identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* må ha tillatelsene **Storage Blob-databidragsyter** på Azure Data Lake Storage Gen2-kontoen der dataene er plassert og koblet til Azure Synapse-arbeidsområdet. Finn ut mer om hvordan du [bruker Azure Portal til å tilordne en Azure-rolle for tilgang til blob- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [tillatelsene for Storage Blob-databidragsyter](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- I Azure Synapse workspace må *tjenestekontohaveren for Customer Insights* som er Dynamics 365 AI for Customer Insights, være tildelt rollen **Synapse-administrator**. Hvis du vil ha mer informasjon, kan du se [Slik konfigurerer du tilgangskontroll for Synapse-arbeidsområdet](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Hvis Customer Insights-miljøet lagrer data i din [egen Azure Data Lake Storage](own-data-lake-storage.md) trenger brukeren som konfigurerer tilkoblingen til Azure Synapse Analytics, minst den innebygde rollen **Leser** på Data Lake Storage-kontoen. Hvis du vil ha mer informasjon, kan du se [Tilordne Azure-roller ved hjelp av Azure Portal](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Koble deg til datasjødatabasen i Azure Synapse Analytics

1. Gå til **Data** > **Datakilder**.

1. Velg **Legg til datakilde**.

1. Velg metoden **Azure Synapse Analytics (forhåndsversjon)**.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialogboks for tilkobling til Synapse Analytics-data":::
  
1. Angi et **Navn** for datakilden og en valgfri **beskrivelse**.

1. Velg en [tilgjengelig tilkobling](connections.md) til Azure Synapse Analytics eller [opprett en ny en](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Velg en **Database** fra arbeidsområdet som er koblet til den valgte Azure Synapse Analytics-tilkoblingen, og velg **Neste**. For øyeblikket støtter vi bare databasetypen *Sjødatabase*.

1. Velg enhetene som skal registreres fra den tilkoblede databasen, og velg **Neste**.

1. Du kan eventuelt velge dataenhetene du vil tillate dataprofilering på.

1. Velg **Lagre** for å ta i bruk valget, og start registreringen av dataene fra den nylig opprettede datakilden koblet til tabellene for Lake Database i Azure Synapse Analytics. Siden **Datakilder** åpnes med den nye datakilde i statusen **Oppdaterer**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan ta tid å laste inn data. Etter en vellykket oppdatering kan de innhentede dataene gjennomgås fra [**Enheter**](entities.md)-siden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
