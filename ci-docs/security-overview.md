---
title: Sikkerhetsinnstillinger i Dynamics 365 Customer Insights
description: Finn ut mer om sikkerhetsinnstillinger i Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653737"
---
# <a name="security-overview-page"></a>Oversiktsside for sikkerhet

Siden **Sikkerhet** viser alternativer for å konfigurere brukertillatelser og funksjoner som bidrar til å gjøre Dynamics 365 Customer Insights sikrere. Bare administratorer har tilgang til denne siden. 

Gå til **Administrator** > **Sikkerhet** for å konfigurere innstillingene.

Siden **Sikkerhet** inneholder følgende faner:
- [Brukere](#users-tab)
- [APIer](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Brukere-fanen

Tilgang til Customer Insights er begrenset til brukere i organisasjonen som ble lagt til i programmet av en administrator. I fanen **Brukere** kan du administrere brukertilgang og deres tillatelser. Du finner mer informasjon under [Brukertillatelser](permissions.md).

## <a name="apis-tab"></a>Fanen API-er

Vis og administrer nøklene for å bruke [API-ene for Customer Insights](apis.md) med dataene i miljøet.

Du kan opprette nye primære og sekundære nøkler ved å velge **Regenerer primær** eller **Regenerer sekundær**. 

Hvis du vil blokkere API-tilgang til miljøet, velger du **Deaktiver**. Hvis API-er er deaktivert, kan du velge **Aktiver** for å gi tilgang på nytt.

## <a name="key-vault-tab"></a>Fanen Key Vault

Med fanen **Key Vault** kan du koble deg til og administrere ditt eget [Azure Key Vault](/azure/key-vault/general/basic-concepts) til miljøet.
Det dedikerte key vault kan brukes til å fase og bruke hemmeligheter i overholdelsesgrensen for en organisasjon. Customer Insights kan bruke hemmelighetene i Azure Key Vault til å [konfigurere tilkoblinger](connections.md) tredjepartssystemer.

Hvis du vil ha mer informasjon, kan du se [Ta med ditt eget Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
