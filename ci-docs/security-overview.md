---
title: Konfigurer sikkerhetsinnstillinger
description: Finn ut mer om sikkerhetsinnstillinger i Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387261"
---
# <a name="configure-security-settings"></a>Konfigurer sikkerhetsinnstillinger

Administrer API-nøkler, få tilgang til kundedata og konfigurer en Azure Private Link.

## <a name="manage-api-keys"></a>Administrer API-nøkler

Vis og administrer nøklene for å bruke [API-ene for Customer Insights](apis.md) med dataene i miljøet.

1. Gå til **Administrator** > **Sikkerhet**, og velg fanen **APIer**.

1. Hvis API-tilgang til miljøet ikke er konfigurert, velger du **Aktiver**. Eller hvis du vil blokkere API-tilgang til miljøet, velger du **Deaktiver** og bekrefter.

1. Administrer de primære og sekundære API-nøklene:

   1. Velg **Vis**-symbolet for å vise den primære eller sekundære API-nøkkelen.

   1. Velg **Kopier**-symbolet for å kopiere den primære eller sekundære API-nøkkelen.

   1. Du kan opprette nye primære eller sekundære API-nøkler ved å velge **Regenerer primær** eller **Regenerer sekundær**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Få sikker tilgang til kundedata med Customer Lockbox (forhåndsversjon)

Customer Insights bruker Power Platform Customer Lockbox-funksjonen. Customer Lockbox har et grensesnitt for å se gjennom og godkjenne (eller avvise) datatilgangsforespørsler. Disse forespørslene oppstår når datatilgang til kundedata er nødvendig for å avslutte en kundestøttesak. Hvis du vil bruke denne funksjonen, må Customer Insights ha en eksisterende tilkobling til et Microsoft Dataverse-miljø i leieren.

Hvis du vil ha mer informasjon om Customer Lockbox, kan du se [sammendraget](/power-platform/admin/about-lockbox#summary) for Power Platform Customer Lockbox. Artikkelen beskriver også [arbeidsflyten](/power-platform/admin/about-lockbox#workflow) og det nødvendige [oppsettet](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) for å aktivere Customer Lockbox.

> [!IMPORTANT]
> Globale administratorer for Power Platform eller Power Platform-administratorer kan godkjenne Customer Lockbox-forespørsler som er utstedt for Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Konfigurer en Azure Private Link

[Azure Private Link](/azure/private-link/private-link-overview) lar Customer Insights kobles seg til Azure Data Lake Storage-kontoen din over et privat endepunkt i det virtuelle nettverket. For data i en lagringskonto, som ikke er eksportert for offentlig Internett, kan Private Link aktivere tilkoblingen til det begrensede nettverket.

> [!IMPORTANT]
> Minimumskrav for rolle for å konfigurere en Private Link-tilkobling:
>
> - Customer Insights: administrator
> - Azure-innebygde rolle: [Lagringskontobidragsyter](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Tillatelser for egendefinert Azure-rolle: [Microsoft.Storage/storageAccounts/read og Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. I Customer Insights går du til **Administrator** > **Sikkerhet**, og deretter velger du kategorien **Private koblinger**.

1. Velg **Legg til Private Link**.

   Ruten **Legg til Private Link** viser lagringskontoer fra leieren som du har tillatelse til å se.

1. Velg abonnementet, ressursgruppen og lagringskontoen.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Lagre**.

1. Gå til Data Lake Storage-kontoen, og åpne koblingen som vises på skjermen.

1. Godkjenn den private koblingen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
