---
title: Eksporter Customer Insights-data til Azure Synapse Analytics
description: Finn ut hvordan du konfigurerer tilkoblingen til Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 772fe0978362ccd829077a8133e2a3e74043f3f8
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741515"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Eksporter data til Azure Synapse Analytics (forhåndsversjon)

Azure Synapse er en analysetjeneste som akselererer tid til innsikt på tvers av datalagre og store datasystemer. Du kan ta inn og bruke Customer Insights-dataene i [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Forutsetninger

Følgende forhåndskrav må oppfylles for å konfigurere tilkoblingen fra Customer Insights til Azure Synapse.

> [!NOTE]
> Pass på at du angir alle **rolletilordninger** slik det er beskrevet.  

## <a name="prerequisites-in-customer-insights"></a>Forhåndskrav i Customer Insights

* Azure Active Directory-brukerkontoen (AD) har en **administratorrolle** i Customer Insights. Du finner ut mer om å [angi brukertillatelser](permissions.md#assign-roles-and-permissions).

I Azure: 

- Et aktivt Azure-abonnement.

- Hvis du bruker en ny Azure Data Lake Storage Gen2-konto, må *tjenestekontohaveren for Customer Insights* ha sikkerhetstillatelsene **Storage Blob-databidragsyter**. Finn ut mer om å [koble til en Azure Data Lake Storage Gen2-konto med Azure-tjenestekontohaver for Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **må ha** [hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace) aktivert.

- På ressursgruppen der Azure Synapse workspace er plassert, må *tjenestekontohaveren* og *Azure AD-brukeren med administratortillatelser i Customer Insights* minst være tildelt **Leser**-tillatelser. Hvis du vil ha mer informasjon, kan du se [Tilordne Azure-roller ved hjelp av Azure Portal](/azure/role-based-access-control/role-assignments-portal).

- *Azure AD-brukeren med administratortillatelser i Customer Insights* må ha tillatelsene **Storage Blob-databidragsyter** på Azure Data Lake Storage Gen2-kontoen der dataene er plassert og koblet til Azure Synapse workspace. Finn ut mer om hvordan du [bruker Azure Portal til å tilordne en Azure-rolle for tilgang til blob- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [tillatelsene for Storage Blob-databidragsyter](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse-arbeidsområdeadministrert identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* må ha tillatelsene **Storage Blob-databidragsyter** på Azure Data Lake Storage Gen2-kontoen der dataene er plassert og koblet til Azure Synapse-arbeidsområdet. Finn ut mer om hvordan du [bruker Azure Portal til å tilordne en Azure-rolle for tilgang til blob- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [tillatelsene for Storage Blob-databidragsyter](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- I Azure Synapse workspace må *tjenestekontohaveren for Customer Insights* være tildelt rollen **Synapse-administrator**. Hvis du vil ha mer informasjon, kan du se [Slik konfigurerer du tilgangskontroll for Synapse-arbeidsområdet](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Konfigurer tilkoblingen og eksporter til Azure Synapse

### <a name="configure-a-connection"></a>Konfigurer en tilkobling

Når du skal opprette en tilkobling, trenger tjenestekontohaveren og brukerkontoen i Customer Insights **Leser**-tillatelser i *ressursgruppen* der arbeidsområdet Synapse Analytics er plassert. Tjenestekontohaveren og brukeren i arbeidsområdet Synapse Analytics trenger i tillegg tillatelsene **Synapse-administrator**. 

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Azure Synapse Analytics** eller velg **Konfigurer** på flisen **Azure Synapse Analytics** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i Visningsnavn-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg eller søk etter abonnementet du vil bruke Customer Insights-dataene i. Så snart et abonnement er valgt, kan du også velge **Arbeidsområde**, **Lagringskonto** og **Beholder**.

1. Velg **Lagre** for å lagre tilkoblingen.

### <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil konfigurere eksporten med en delt tilkobling, må du minst ha **Bidragsyter**-tillatelser i Customer Insights. Hvis du vil ha mer informasjon, kan du se [tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport** for å opprette en ny eksport.

1. Velg en tilkobling fra **Azure Synapse Analytics**-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen [tilkoblinger](connections.md) av denne typen tilgjengelige for deg.

1. Angi et gjenkjennelig **visningsnavn** for eksporten og et **databasenavn**.

1. Velg hvilke enheter du vil eksportere til Azure Synapse Analytics.
   > [!NOTE]
   > Datakilder som er basert på en [Common Data Model-mappe](connect-common-data-model.md), støttes ikke.

2. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand).

Hvis du vil spørre etter data som ble eksportert til Synapse Analytics, trenger du tilgangen **Leser for Storage Blob Data** til mållageret i arbeidsområdet for eksporter. 

### <a name="update-an-export"></a>Oppdater en eksport

1. Gå til **Data** > **Eksporter**.

1. Velg **Rediger** på eksporten du vil oppdatere.

   - **Legg til** eller **Fjern** enheter fra utvalget. Hvis enheter fjernes fra utvalget, slettes de ikke fra Synapse Analytics-databasen. Fremtidige data oppdateres imidlertid ikke for de fjernede enhetene i databasen.

   - **Endring av databasenavnet** oppretter en ny Synapse Analytics-database. Databasen med navnet som ble konfigurert før, vil ikke motta oppdateringer i fremtidige oppdateringer.