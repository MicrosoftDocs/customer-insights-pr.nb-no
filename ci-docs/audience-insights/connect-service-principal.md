---
title: Koble til en Azure Data Lake Storage-konto ved hjelp av en tjenestekontohaver
description: Bruk en Azure-tjenestekontohaver til å koble til din egen datasjø.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461160"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Koble til en Azure Data Lake Storage-konto ved hjelp av en Azure-tjenestekontohaver
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Automatiske verktøy som bruker Azure-tjenester, bør alltid ha begrensede tillatelser. I stedet for at programmer skal logges på som en bruker med full rettigheter, tilbyr Azure tjenestekontohavere. Les videre for å lære hvordan du kobler Dynamics 365 Customer Insights til en Azure Data Lake Storage-konto ved hjelp av en Azure-tjenestekontohaver i stedet for lagringskontonøkler. 

Du kan bruke tjenestekontohaveren til sikkert å [legge til eller redigere en Common Data Service-mappe som en datakilde](connect-common-data-model.md) eller [opprette eller oppdatere et miljø](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Data Lake Storage-konto som skal bruke<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> tjenestekontohaveren må ha [hierarkisk navneområde aktivert](/azure/storage/blobs/data-lake-storage-namespace).
> - Du trenger administratortillatelser for Azure-abonnementet for å opprette tjenestekontohaveren.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Opprett en Azure-tjenestekontohaver for Customer Insights

Før du oppretter en ny tjenestekontohaver for målgruppeinnsikt eller engasjementsinnsikt, bør du kontrollere om den allerede finnes i organisasjonen.

### <a name="look-for-an-existing-service-principal"></a>Se etter en eksisterende tjenestekontohaver

1. Gå til [Azure-administratorportalen](https://portal.azure.com), og logg på organisasjonen.

2. Velg **Azure Active Directory** under **Azure-tjenester**.

3. Under **Administrer** velger du **Enterprise-programmer**.

4. Søk etter Microsoft-<!--note from editor: Via Microsoft Writing Style Guide.--> program-ID:
   - Målgruppeinnsikt: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` med navnet `Dynamics 365 AI for Customer Insights`
   - Engasjementsinnsikt: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` med navnet `Dynamics 365 AI for Customer Insights engagement insights`

5. Hvis du finner en samsvarende oppføring, betyr det at tjenestekontohaveren allerede finnes. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skjermbilde som viser en eksisterende tjenestekontohaver.":::
   
6. Hvis ingen resultater returneres, oppretter du en ny tjenestekontohaver.

>[!NOTE]
>Vi foreslår at du legger til begge appene i tjenestekontohaveren for å få brukt alle funksjonene i Dynamics 365 Customer Insights.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Opprett en ny tjenestekontohaver
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Installer den nyeste versjonen av Azure Active Directory PowerShell for Graph. Hvis du vil ha mer informasjon, kan du gå til [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Velg Windows-tasten på tastaturet på PC-en, søk etter **Windows PowerShell**, og velg **Kjør som administrator**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. I PowerShell-vinduet som åpnes, skriver du inn `Install-Module AzureAD`.

2. Opprett tjenestekontohaveren for Customer Insights med Azure AD PowerShell-modulen.

   1. I PowerShell-vinduet skriver du inn `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Erstatt *"[your tenant ID]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> med den faktiske ID-en for leieren der du vil opprette tjenestekontohaveren. Parameteren for miljønavnet `AzureEnvironmentName` er valgfri.
  
   1. Angi `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Denne kommandoen oppretter tjenestekontohaveren for målgruppeinnsikt i den valgte leieren. 

   1. Angi `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Denne kommandoen oppretter tjenestekontohaver for engasjementsinnsikt<!--note from editor: Edit okay?--> på den valgte leieren.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Gi tillatelser til tjenestekontohaveren for tilgang til lagringskontoen

Gå til Azure-portalen for å gi tillatelser til tjenestekontohaveren for lagringskontoen du vil bruke i målgruppeinnsikt.

1. Gå til [Azure-administratorportalen](https://portal.azure.com), og logg på organisasjonen.

1. Åpne lagringskontoen du vil at tjenestekontohaveren for målgruppeinnsikt skal ha tilgang til.

1. Velg **Access control (IAM)** i ruten til venstre, og velg deretter **Legg til** > **Legg til rolletilordning**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skjermbilde som viser Azure Portal når du legger til en rolletilordning.":::

1. Angi følgende egenskaper i ruten **Legg til rolletilordning**:
   - Rolle: **Storage Blob-databidragsyter**
   - Tilordne tilgang til: **Bruker, gruppe eller tjenestekontohaver**
   - Velg: **Dynamics 365 AI for Customer Insights** og **Dynamics 365 AI for Customer Insights-engasjementsinnsikt** (de to [tjenestekontohaverne](#create-a-new-service-principal) du opprettet tidligere i denne fremgangsmåten)

1.  Velg **Lagre**.

Det kan ta opptil 15 minutter å overføre endringene.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Skriv inn Azure-ressurs-ID-en eller Azure-abonnementsdetaljene i lagringskontovedlegget for målgruppeinnsikt

Du kan<!--note from editor: Edit suggested only if this section is optional.--> legge ved en Data Lake Storage-konto i målgruppeinnsikt for å [lagre utdata](manage-environments.md) eller [bruke den som en datakilde](connect-common-data-service-lake.md). Med dette alternativet kan du velge mellom en ressursbasert eller en abonnementsbasert metode. Følg fremgangsmåten i en av delene nedenfor, avhengig av hvilken metode du velger.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Ressursbasert tilkobling til lagringskonto

1. Gå til [Azure-administrasjonsportalen](https://portal.azure.com), logg på abonnementet, og åpne lagringskontoen.

1. Gå til **Innstillinger** > **Egenskaper** i ruten til venstre.

1. Kopier ressurs-ID-verdien for lagringskontoen.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopier ressurs-ID-en for lagringskontoen.":::

1. I målgruppeinnsikt setter du inn ressurs-ID-en i ressursfeltet som vises på tilkoblingsskjermbildet for lagringskontoen.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Angi informasjon om ressurs-ID-en for lagringskontoen.":::   

1. Fortsett med resten av trinnene i målgruppeinnsikt for å legge ved lagringskontoen.

### <a name="subscription-based-storage-account-connection"></a>Abonnementsbasert tilkobling til lagringskonto

1. Gå til [Azure-administrasjonsportalen](https://portal.azure.com), logg på abonnementet, og åpne lagringskontoen.

1. Gå til **Innstillinger** > **Egenskaper** i ruten til venstre.

1. Gå gjennom **abonnementet**, **ressursgruppen** og **navnet** for lagringskontoen for å forsikre deg om at du velger de riktige verdiene i målgruppeinnsikt.

1. I målgruppeinnsikt velger du verdiene for de tilsvarende feltene når du legger ved lagringskontoen.

1. Fortsett med resten av trinnene i målgruppeinnsikt for å legge ved lagringskontoen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]