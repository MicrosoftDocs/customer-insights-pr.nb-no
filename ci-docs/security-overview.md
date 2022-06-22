---
title: Sikkerhetsinnstillinger for Customer Insights
description: Finn ut mer om sikkerhetsinnstillinger i Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947427"
---
# <a name="security-settings-in-customer-insights"></a>Sikkerhetsinnstillinger for Customer Insights

Siden **Sikkerhet** viser alternativer for å konfigurere brukertillatelser og funksjoner som bidrar til å gjøre Dynamics 365 Customer Insights sikrere. Bare administratorer har tilgang til denne siden.

Gå til **Administrator** > **Sikkerhet** for å konfigurere innstillingene.

Siden **Sikkerhet** inneholder følgende faner:

- [Brukere](#users-tab)
- [APIer](#apis-tab)
- [Private koblinger](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Få sikker tilgang til kundedata med Customer Lockbox (forhåndsversjon)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Brukere-fanen

Tilgang til Customer Insights er begrenset til brukere i organisasjonen som ble lagt til i programmet av en administrator. I fanen **Brukere** kan du administrere brukertilgang og deres tillatelser. Du finner mer informasjon under [Brukertillatelser](permissions.md).

## <a name="apis-tab"></a>Fanen API-er

Vis og administrer nøklene for å bruke [API-ene for Customer Insights](apis.md) med dataene i miljøet.

Du kan opprette nye primære og sekundære nøkler ved å velge **Regenerer primær** eller **Regenerer sekundær**. 

Hvis du vil blokkere API-tilgang til miljøet, velger du **Deaktiver**. Hvis API-er er deaktivert, kan du velge **Aktiver** for å gi tilgang på nytt.

## <a name="private-links-tab"></a>Private koblinger-fane

[Azure Private Link](/azure/private-link/private-link-overview) lar Customer Insights kobles seg til Azure Data Lake Storage-kontoen din over et privat endepunkt i det virtuelle nettverket. For data i en lagringskonto, som ikke er eksportert for offentlig Internett, kan Private Link aktivere tilkoblingen til det begrensede nettverket.

> [!IMPORTANT]
> Minimumskrav for rolle for å konfigurere en Private Link-tilkobling:
>
> - Customer Insights: administrator
> - Azure-innebygde rolle: [Lagringskontobidragsyter](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Tillatelser for egendefinert Azure-rolle: [Microsoft.Storage/storageAccounts/read og Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Konfigurering av Private Link i Customer Insights er en totrinnsprosess. Først starter du opprettingen av en Private Link fra **Administrasjon** > **Sikkerhet** > **Private Links** i Customer Insights. Ruten **Legg til Private Link** viser lagringskontoer fra leieren som du har tillatelse til å se. Velg lagringskontoen, og gi samtykke til å opprette Private Link.

Deretter må du godkjenne Private Link på Data Lake Storage-kontosiden. Åpne koblingen som presenteres på skjermen for å godkjenne Private Link.

## <a name="key-vault-tab"></a>Fanen Key Vault

Med fanen **Key Vault** kan du koble deg til og administrere ditt eget [Azure Key Vault](/azure/key-vault/general/basic-concepts) til miljøet.
Det dedikerte key vault kan brukes til å fase og bruke hemmeligheter i overholdelsesgrensen for en organisasjon. Customer Insights kan bruke hemmelighetene i Azure Key Vault til å [konfigurere tilkoblinger](connections.md) tredjepartssystemer.

Hvis du vil ha mer informasjon, kan du se [Ta med ditt eget Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Få sikker tilgang til kundedata med Customer Lockbox (forhåndsversjon)

Customer Insights bruker Power Platform Customer Lockbox-funksjonen. Customer Lockbox har et grensesnitt for å se gjennom og godkjenne (eller avvise) datatilgangsforespørsler. Disse forespørslene oppstår når datatilgang til kundedata er nødvendig for å avslutte en kundestøttesak. Hvis du vil bruke denne funksjonen, må Customer Insights ha en eksisterende tilkobling til et Microsoft Dataverse-miljø i leieren.

Hvis du vil ha mer informasjon om Customer Lockbox, kan du se [sammendraget](/power-platform/admin/about-lockbox#summary) for Power Platform Customer Lockbox. Artikkelen beskriver også [arbeidsflyten](/power-platform/admin/about-lockbox#workflow) og det nødvendige [oppsettet](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) for å aktivere Customer Lockbox.

> [!IMPORTANT]
> Globale administratorer for Power Platform eller Power Platform-administratorer kan godkjenne Customer Lockbox-forespørsler som er utstedt for Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
