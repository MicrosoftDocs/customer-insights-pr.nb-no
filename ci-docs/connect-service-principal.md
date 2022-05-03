---
title: Koble til en Azure Data Lake Storage-konto ved hjelp av en tjenestekontohaver
description: Bruk en Azure-tjenestekontohaver til å koble til din egen datasjø.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 1dd99edc327bd41b0442b390f2e4f8664269f553
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646874"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Koble til en Azure Data Lake Storage-konto ved hjelp av en Azure-tjenestekontohaver

Denne artikkelen beskriver hvordan du kobler Dynamics 365 Customer Insights til en Azure Data Lake Storage konto ved hjelp av en Azure-tjenestekontohaver i stedet for lagringskontonøkler. 

Automatiske verktøy som bruker Azure-tjenester, bør alltid ha begrensede tillatelser. I stedet for at programmer skal logges på som en bruker med full rettigheter, tilbyr Azure tjenestekontohavere. Du kan bruke tjenestekontohavere til sikkert å [legge til eller redigere en Common Data Model-mappe som en datakilde](connect-common-data-model.md) eller [opprette eller oppdatere et miljø](create-environment.md).

> [!IMPORTANT]
> - Data Lake Storage-kontoen som skal bruke tjenestekontohaveren, må være Gen2 og ha [hierarkisk navneområde aktivert](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1-lagringskontoer støttes ikke.
> - Du må ha administratortillatelser for Azure-abonnementet for å opprette en tjenestekontohaver.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Opprett en Azure-tjenestekontohaver for Customer Insights

Før du oppretter en ny tjenestekontohaver for Customer Insights, kontrollerer du om den allerede finnes i organisasjonen.

### <a name="look-for-an-existing-service-principal"></a>Se etter en eksisterende tjenestekontohaver

1. Gå til [Azure-administratorportalen](https://portal.azure.com), og logg på organisasjonen.

2. Velg **Azure Active Directory** under **Azure-tjenester**.

3. Under **Administrer** velger du **Enterprise-programmer**.

4. Søk etter Microsoft-program-ID-en `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` med navnet `Dynamics 365 AI for Customer Insights`.

5. Hvis du finner en samsvarende oppføring, betyr det at tjenestekontohaveren allerede finnes. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skjermbilde som viser en eksisterende tjenestekontohaver.":::
   
6. Hvis ingen resultater returneres, oppretter du en ny tjenestekontohaver.

### <a name="create-a-new-service-principal"></a>Opprett en ny tjenestekontohaver

1. Installer den nyeste versjonen av Azure Active Directory PowerShell for Graph. Hvis du vil ha mer informasjon, kan du gå til [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Velg Windows-tasten på tastaturet på PC-en, søk etter **Windows PowerShell**, og velg **Kjør som administrator**.
   
   1. I PowerShell-vinduet som åpnes, skriver du inn `Install-Module AzureAD`.

2. Opprett tjenestekontohaveren for Customer Insights med Azure AD PowerShell-modulen.

   1. I PowerShell-vinduet skriver du inn `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Bytt ut *[katalog-ID]* med den faktiske katalog-ID-en for Azure-abonnementet der du vil opprette tjenestekontohaveren. Parameteren for miljønavnet `AzureEnvironmentName` er valgfri.
  
   1. Angi `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Denne kommandoen oppretter tjenestesjefen for Customer Insights i det valgte Azure-abonnementet. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Gi tillatelser til tjenestekontohaveren for tilgang til lagringskontoen

Gå til Azure-portalen for å gi tillatelser til tjenestekontohaveren for lagringskontoen du vil bruke i Customer Insights.

1. Gå til [Azure-administratorportalen](https://portal.azure.com), og logg på organisasjonen.

1. Åpne lagringskontoen du vil at tjenestekontohaveren for Customer Insights skal ha tilgang til.

1. Velg **Access control (IAM)** i ruten til venstre, og velg deretter **Legg til** > **Legg til rolletilordning**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skjermbilde som viser Azure Portal når du legger til en rolletilordning.":::

1. Angi følgende egenskaper i ruten **Legg til rolletilordning**:
   - Rolle: **Storage Blob-databidragsyter**
   - Tilordne tilgang til: **Bruker, gruppe eller tjenestekontohaver**
   - Velg medlemmer: **Dynamics 365 AI for Customer Insights** ([tjenestekontohaveren](#create-a-new-service-principal) du opprettet tidligere i denne prosedyren)

1.  Velg **Se gjennom + tildel**.

Det kan ta opptil 15 minutter å overføre endringene.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Angi Azure-ressurs-ID-en eller Azure-abonnementsdetaljene i vedlegget til lagringskonto i Customer Insights

Du kan legge ved en Data Lake Storage-konto i Customer Insights for [å lagre utdata](manage-environments.md) eller [bruke den som en datakilde](connect-dataverse-managed-lake.md). Med dette alternativet kan du velge mellom en ressursbasert eller en abonnementsbasert metode. Følg fremgangsmåten i en av delene nedenfor, avhengig av hvilken metode du velger.

### <a name="resource-based-storage-account-connection"></a>Ressursbasert tilkobling til lagringskonto

1. Gå til [Azure-administrasjonsportalen](https://portal.azure.com), logg på abonnementet, og åpne lagringskontoen.

1. Gå til **Innstillinger** > **Egenskaper** i ruten til venstre.

1. Kopier ressurs-ID-verdien for lagringskontoen.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopier ressurs-ID-en for lagringskontoen.":::

1. I Customer Insights setter du inn ressurs-ID-en i ressursfeltet som vises på tilkoblingsskjermbildet for lagringskontoen.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Angi informasjon om ressurs-ID-en for lagringskontoen.":::   

1. Fortsett med de resterende trinnene i Customer Insights for å legge ved lagringskontoen.

### <a name="subscription-based-storage-account-connection"></a>Abonnementsbasert tilkobling til lagringskonto

1. Gå til [Azure-administrasjonsportalen](https://portal.azure.com), logg på abonnementet, og åpne lagringskontoen.

1. Gå til **Innstillinger** > **Egenskaper** i ruten til venstre.

1. Gå gjennom **Abonnement**, **Ressursgruppe** og **Navn** på lagringskontoen for å forsikre deg om at du velger de riktige verdiene i Customer Insights.

1. I Customer Insights velger du verdiene for de tilsvarende feltene når du legger ved lagringskontoen.

1. Fortsett med de resterende trinnene i Customer Insights for å legge ved lagringskontoen.


[!INCLUDE [footer-include](includes/footer-banner.md)]