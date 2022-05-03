---
title: Registrer data fra Azure Synapse Analytics
description: Bruk en database i Azure Synapse som en datakilde i Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646863"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Koble til en Azure Synapse-datakilde (forhåndsversjon)

Azure Synapse Analytics er en bedriftsanalysetjeneste som akselererer tid til innsikt på tvers av datalagre og stordatasystemer. Azure Synapse Analytics samler sammen det beste av SQL-teknologi som brukes i bedriftsdatalagring, Spark-teknologier som brukes til stordata, Data Explorer for analyse av logg- og tidsserier, forløp for dataintegrering og ETL/ELT samt grundig integrasjon med andre Azure-tjenester som Power BI, Cosmos DB og AzureML.

Hvis du vil ha mer informasjon, kan du se [Oversikt over Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Krav

Følgende forutsetninger må være oppfylt for å konfigurere tilkoblingen fra Dynamics 365 Customer Insights til Azure Synapse.

> [!IMPORTANT]
> Pass på at du angir alle **rolletilordninger** slik det er beskrevet.  

## <a name="prerequisites-in-customer-insights"></a>Forhåndskrav i Customer Insights

* Du har en **administratorrolle** i Customer Insights. Finn ut mer om [brukertillatelser i Customer Insights](permissions.md#assign-roles-and-permissions).

I Azure: 

- Et aktivt Azure-abonnement.

- Hvis du bruker en ny Azure Data Lake Storage Gen2-konto, må *tjenestekontohaveren for Customer Insights* ha sikkerhetstillatelsene **Storage Blob-databidragsyter**. Finn ut mer om hvordan du [kobler en Azure Data Lake Storage sammen med en tjenestekontohaver for Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **må ha** [hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace) aktivert.

- På ressursgruppen der Azure Synapse workspace er plassert, må *tjenestekontohaveren* og *brukeren for Customer Insights* må være tildelt minst **Leser**-tillatelser. Hvis du vil ha mer informasjon, kan du se [Tilordne Azure-roller ved hjelp av Azure Portal](/azure/role-based-access-control/role-assignments-portal).

- *Brukeren* må ha tillatelsene **Storage Blob-databidragsyter** på Azure Data Lake Storage Gen2-kontoen der dataene er plassert og koblet til Azure Synapse-arbeidsområdet. Finn ut mer om hvordan du [bruker Azure Portal til å tilordne en Azure-rolle for tilgang til blob- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [tillatelsene for Storage Blob-databidragsyter](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse-arbeidsområdeadministrert identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* må ha tillatelsene **Storage Blob-databidragsyter** på Azure Data Lake Storage Gen2-kontoen der dataene er plassert og koblet til Azure Synapse-arbeidsområdet. Finn ut mer om hvordan du [bruker Azure Portal til å tilordne en Azure-rolle for tilgang til blob- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [tillatelsene for Storage Blob-databidragsyter](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- I Azure Synapse workspace må *tjenestekontohaveren for Customer Insights* være tildelt rollen **Synapse-administrator**. Hvis du vil ha mer informasjon, kan du se [Slik konfigurerer du tilgangskontroll for Synapse-arbeidsområdet](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Koble til datasjødatabaser i Azure Synapse Analytics

1. Gå til **Data** > **Datakilder**.

1. Velg **Legg til datakilde**.

1. Velg metoden **Azure Synapse Analytics (forhåndsversjon)**.

1. Angi et **Navn** for datakilden, og velg deretter **Neste** for å opprette datakilden. 

1. Velg en [tilgjengelig tilkobling](connections.md) til Azure Synapse Analytics eller opprett en ny en.

1. Velg en **Lage Database** fra arbeidsområdet som er koblet til den valgte Azure Synapse Analytics-tilkoblingen, og velg **Neste**.

1. Velg enhetene som skal registreres fra den tilkoblede databasen. 

1. Du kan eventuelt velge dataenhetene du vil tillate dataprofilering på. 

1. Velg **Lagre** for å ta i bruk valget, og start registreringen av dataene fra den nylig opprettede datakilden koblet til tabellene for Lake Database i Azure Synapse Analytics.
