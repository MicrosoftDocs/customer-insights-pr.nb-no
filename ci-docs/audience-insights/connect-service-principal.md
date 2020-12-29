---
title: Koble til en Azure Data Lake Storage Gen2-konto med en tjenestekontohaver
description: Bruk en Azure-tjenestekontohaver for målgruppeinnsikt for å koble deg til din egen Data Lake-forekomst når du legger den ved målgruppeinnsikt.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644100"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Koble til en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver for målgruppeinnsikt

Automatiske verktøy som bruker Azure-tjenester, bør alltid ha begrensede tillatelser. I stedet for at programmer skal logges på som en bruker med full rettigheter, tilbyr Azure tjenestekontohavere. Les videre for å lære hvordan du kobler til målgruppeinnsikt med en Azure Data Lake Storage Gen2-konto ved hjelp av en Azure-tjenestekontohaver i stedet for lagringskontonøkler. 

Du kan bruke tjenestekontohaveren til å [legge til eller redigere en Common Data Model-mappe som en datakilde](connect-common-data-model.md) på en sikkwer måte eller [opprette et nytt eller oppdatere et eksisterende miljø](manage-environments.md#create-an-environment-in-an-existing-organization).

Du trenger administratortillatelser for Azure-abonnementet for å opprette tjenestekontohaveren.

## <a name="create-azure-service-principal-for-audience-insights"></a>Opprette Azure-tjenestekontohaver for målgruppeinnsikt

Før du oppretter en ny tjenestekontohaver for målgruppeinnsikt, må du kontrollere om det allerede finnes en i organisasjonen.

### <a name="look-for-an-existing-service-principal"></a>Se etter en eksisterende tjenestekontohaver

1. Gå til [Azure-administratorportalen](https://portal.azure.com), og logg på organisasjonen.

2. Velg **Azure Active Directory** fra Azure-tjenestene.

3. Under **Administrer** velger du **Enterprise-programmer**.

4. Søk etter førsteparts program-ID-en for målgruppeinnsikt `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` eller navnet `Dynamics 365 AI for Customer Insights`.

5. Hvis du finner en samsvarende oppføring, betyr det at tjenestekontohaveren for målgruppeinnsikt finnes. Du trenger ikke å opprette den på nytt.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skjermbilde som viser den eksisterende tjenestekontohaveren.":::
   
6. Hvis ingen resultater returneres, oppretter du en ny tjenestekontohaver.

### <a name="create-a-new-service-principal"></a>Opprett en ny tjenestekontohaver

1. Installer den nyeste versjonen av **Azure Active Directory PowerShell for Graph**. Hvis du vil ha mer informasjon, kan du se [Installere Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - På PC-en velger du Windows-tasten på tastaturet, og søker etter **Windows PowerShell** og **Kjør som administrator**.
   
   - I PowerShell-vinduet som åpnes, skriver du inn `Install-Module AzureAD`.

2. Opprett tjenestekontohaveren for målgruppeinnsikt ved hjelp av Azure AD PowerShell-modulen.
   - I PowerShell-vinduet skriver du inn `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Erstatt "din leier-ID" med den faktiske ID-en for leieren din der du vil opprette tjenestekontohaveren. Parameteren for miljønavnet `AzureEnvironmentName` er valgfri.
  
   - Angi `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Denne kommandoen oppretter tjenestekontohaveren for målgruppeinnsikt i den valgte leieren.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Gi tillatelser til tjenestekontohaveren for tilgang til lagringskontoen

Gå til Azure-portalen for å gi tillatelser til tjenestekontohaveren for lagringskontoen du vil bruke i målgruppeinnsikt.

1. Gå til [Azure-administratorportalen](https://portal.azure.com), og logg på organisasjonen.

1. Åpne lagringskontoen du vil at tjenestekontohaveren for målgruppeinnsikt skal ha tilgang til.

1. Velg **Tilgangskontroll (IAM)** fra navigasjonsruten, og velg **Legg til** > **Legg til rolletilordning**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skjermbilde som viser Azure Portal når en rolletildeling legges til.":::
   
1. I ruten **Legg til rolletildeling** angir du følgende egenskaper:
   - Rolle: *Storage Blob-databidragsyter*
   - Tilordne tilgang til: *Bruker, gruppe eller tjenestekontohaver*
   - Velg: *Dynamics 365 AI for Customer Insights* ([tjenestekontohaveren du opprettet](#create-a-new-service-principal))

1.  Velg **Lagre**.

Det kan ta opptil 15 minutter å overføre endringene.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Skriv inn Azure-ressurs-ID-en eller Azure-abonnementsdetaljene i lagringskontovedlegget for målgruppeinnsikt.

Legg ved en Azure Data Lake-lagringskonto i målgruppeinnsikt for å [lagre utdata](manage-environments.md) eller [bruke den som en datakilde](connect-common-data-service-lake.md). Hvis du velger Azure Data Lake-alternativet, kan du velge mellom en ressursbasert eller abonnementsbasert tilnærming.

Følg fremgangsmåten nedenfor for å gi den nødvendige informasjonen på den valgte tilnærmingen.

### <a name="resounce-based-storage-account-connection"></a>Ressursbasert tilkobling til lagringskonto

1. Gå til [Azure-administrasjonsportalen](https://portal.azure.com), logg på abonnementet, og åpne lagringskontoen.

1. Gå til **Innstillinger** > **Egenskaper** i navigasjonsruten.

1. Kopier ressurs-ID-verdien for lagringskontoen.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopier ressurs-ID-en for lagringskontoen.":::

1. I målgruppeinnsikt setter du inn ressurs-ID-en i ressursfeltet som vises i skjermbildet for tilkobling til lagringskontoen.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Angi informasjon om ressurs-ID-en for lagringskontoen.":::   
   
1. Fortsett med resten av trinnene i målgruppeinnsikt for å legge ved lagringskontoen.

### <a name="subscription-based-storage-account-connection"></a>Abonnementsbasert tilkobling til lagringskonto

1. Gå til [Azure-administrasjonsportalen](https://portal.azure.com), logg på abonnementet, og åpne lagringskontoen.

1. Gå til **Innstillinger** > **Egenskaper** i navigasjonsruten.

1. Gå gjennom **abonnementet**, **ressursgruppen** og **navnet** for lagringskontoen for å forsikre deg om at du velger de riktige verdiene i målgruppeinnsikt.

1. I målgruppeinnsikt velger du verdiene eller de tilsvarende feltene når du legger ved lagringskontoen.

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Angi informasjon om ressurs-ID-en for lagringskontoen.":::
   
1. Fortsett med resten av trinnene i målgruppeinnsikt for å legge ved lagringskontoen.
