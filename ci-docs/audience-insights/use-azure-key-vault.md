---
title: Hente ditt eget Azure Key Vault for å administrere hemmeligheter
description: Lær hvordan du konfigurerer Customer Insights til å bruke ditt eget Azure Key Vault.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 5b22c1464b3f089551f485f98d6d93840ff77136
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355903"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Hente ditt eget Azure Key Vault (forhåndsvisning)

Kobling til et dedikert [Azure Key Vault](/azure/key-vault/general/basic-concepts) til et miljø for målgruppeinnsikt hjelper organisasjoner med å oppfylle samsvarskravene.
Det dedikerte key vault kan brukes til å fase og bruke hemmeligheter i overholdelsesgrensen for en organisasjon. Målgruppeinnsikt kan bruke hemmelighetene i Azure Key Vault til å [konfigurere tilkoblinger](connections.md) tredjepartssystemer.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Koble key vault til miljø for målgruppeinnsikt

### <a name="prerequisites"></a>Forutsetninger

Hvis du vil konfigurere key vault i målgruppeinnsikt, må følgende forhåndskrav oppfylles:

- Du må ha et aktivt Azure-abonnement.

- Du har en [Administrator](permissions.md#administrator)-brukerrolle i målgruppeinnsikt. Lær mer om [brukertillatelser i målgruppeinnsikt](permissions.md#assign-roles-and-permissions).

- Du har rollene [Bidragsyter](/azure/role-based-access-control/built-in-roles#contributor) og [Brukertilgangsadministrator](/azure/role-based-access-control/built-in-roles#user-access-administrator) i key vault eller ressursgruppen som key vault tilhører. Hvis du vil ha mer informasjon, kan du gå til [Legge til eller fjerne Azure-rolletilordninger ved hjelp av Azure-portalen](/azure/role-based-access-control/role-assignments-portal). Hvis du ikke har rollen Brukertilgangsadministrator i key vault, må du konfigurere de rollebaserte tilgangskontrolltillatelsene for Azure-tjenestekontohaveren for Dynamics 365 Customer Insights separat. Følg fremgangsmåten for å [bruke en Azure-tjenestekontohaver](connect-service-principal.md) for key vault som skal kobles.

- Key vault må ha deaktivert **Key Vault-brannmuren**.

- Key vault er på samme [Azure-plassering](https://azure.microsoft.com/global-infrastructure/geographies/#overview) som målgruppeinnsiktsmiljøet. Området for miljøet i målgruppen er oppført under **Admin** > **System** > **Om** > **Område**.

### <a name="link-a-key-vault-to-the-environment"></a>Koble et key vault til miljøet

1. Gå til **Admin** > **System**, og velg deretter kategorien **Sikkerhet**.
1. Velg **Oppsett** i flisen **Key Vault**.
1. Velg et **Abonnement**.
1. Velg et key vault fra rullegardinlisten **Key Vault**. Hvis det vises for mange viktige key vaults, velger du en ressursgruppe for å begrense søkeresultatene.
1. Godta erklæringen **Datapersonvern og -samsvar**.
1. Velg **Lagre**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Fremgangsmåte for å konfigurere et koblet key vault i målgruppeinnsikt.":::

**Key Vault**-flisen viser nå det koblede key vault-navnet, ressursgruppen og abonnementet. Den er klar til bruk i tilkoblingsoppsettet.
Hvis du vil ha mer informasjon om hvilke tillatelser i key vault som gis til målgruppeinnsikt, kan du gå til [Tillatelser som gis i key vault til målgruppeinnsikt](#permissions-granted-on-the-key-vault-to-audience-insights) senere i denne artikkelen.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Bruke nøkkelhvelvet i tilkoblingsoppsettet

Når du [konfigurerer tilkoblinger](connections.md) til tredjepartssystemer, kan hemmelighetene fra Key Vault brukes til å konfigurere tilkoblingene.

1. Gå til **Administrator** > **Tilkoblinger**.
1. Velg **Legg til tilkobling**.
1. For de støttede tilkoblingstypene er **Bruk Key Vault** tilgjengelig hvis du koblet til et Key Vault.
1. I stedet for å skrive inn hemmeligheten manuelt, kan du velge det hemmelige navnet som peker til den hemmelige verdien i Key Vault.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Tilkoblingsrute med en SFTP-tilkobling som bruker en Key Vault-hemmelighet.":::

## <a name="supported-connection-types"></a>Støttede tilkoblingstyper

Følgende [eksport](export-destinations.md)-tilkoblinger støttes:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Tillatelser gitt på nøkkelhvelvet til målgruppeinnsikt

Tillatelsene nedenfor gis til målgruppeinnsikt på et koblet Key Vault hvis [Key Vault-tilgangspolicyen](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) eller [Azure-rollebasert tilgangskontroll](/azure/key-vault/general/rbac-guide?tabs=azure-cli) er aktivert.

### <a name="key-vault-access-policy"></a>Tilgangspolicy for Key Vault

| Type        | Tillatelser          |
| ----------- | -------------------- |
| Nøkkel         | [Hent nøkler](/rest/api/keyvault/get-keys), [Hent nøkkel](/rest/api/keyvault/get-key)                                 |
| Hemmelighet      | [Hent hemmeligheter](/rest/api/keyvault/get-secrets), [Hent hemmelighet](/rest/api/keyvault/get-secret)                     |
| Sertifikat | [Hent sertifikater](/rest/api/keyvault/get-certificates), [Hent sertifikat](/rest/api/keyvault/get-certificate) |

De foregående verdiene er minimum for å liste opp og lese under kjøring.

### <a name="azure-role-based-access-control"></a>Azure-rollebasert tilgangskontroll

Brukerrollene Key Vault-leser og Key Vault-hemmeligheter legges til for å gi målgruppeinnsikt. Hvis du vil ha mer informasjon om disse rollene, kan du gå til [de innebygde Azure-rollene for Key Vault-dataplanoperasjoner](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Anbefalinger

- Bruk et separat eller dedikert Key Vault som bare inneholder hemmelighetene som kreves for målgruppeinnsikt. Les mer om hvorfor [separate Key Vault anbefales](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Følg de [beste fremgangsmåtene ved bruk av Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) for kontrolltilgang, sikkerhetskopiering, sporing av endringer og gjenoppretting.

## <a name="frequently-asked-questions"></a>Vanlige spørsmål

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Kan målgruppeinnsikt skrive hemmeligheter eller skrive over hemmeligheter i Key Vault?

Nei. Bare lese- og listetillatelsene som er beskrevet i delen [gitte tillatelser](#permissions-granted-on-the-key-vault-to-audience-insights) tidligere i denne artikkelen, gis til målgruppeinnsikt. Systemet kan ikke legge til, slette eller overskrive hemmeligheter i Key Vault. Det er også årsaken til at du ikke kan angi legitimasjon når en tilkobling bruker Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Kan jeg endre en tilkobling fra å bruke Key Vault-hemmeligheter til standardgodkjenning?

Nei. Du kan ikke gå tilbake til en standardtilkobling etter at du har konfigurert den, ved å bruke en hemmelighet fra et koblet Key Vault. Opprett en separat tilkobling, og slett den gamle hvis du ikke trenger den lenger.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Hvordan kan jeg oppheve tilgang til et viktig Key Vault for målgruppeinnsikt?

Avhengig av om [Tilgangspolicy for Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) eller [Azure-rollebasert tilgangskontroll](/azure/key-vault/general/rbac-guide?tabs=azure-cli) er aktivert, må du fjerne tillatelsene for tjenestekontohaveren `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` med navnet `Dynamics 365 AI for Customer Insights`. Alle tilkoblinger som bruker Key Vault, slutter å fungere.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>En hemmelighet som brukes i en tilkobling, ble fjernet fra Key Vault. Hva kan jeg gjøre?

Et varsel vises i målgruppe når en konfigurert hemmelighet fra Key Vault ikke er tilgjengelig lenger. Aktiver [sletting](/azure/key-vault/general/soft-delete-overview) i nøkkelhvelvet for å gjenopprette hemmeligheter hvis de blir fjernet ved et uhell.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>En tilkobling fungerer ikke, men hemmeligheten min er i Key Vault. Hva kan være årsaken?

Et varsel vises i målgruppeinnsikt når det ikke har tilgang til Key Vault. Grunnen kan være:

- Tillatelsene for tjenestekontohaver for målgruppeinnsikt er fjernet. De må gjenopprettes manuelt.

- Brannmuren i Key Vault er aktivert. Brannmuren må være deaktivert for å gjøre Key Vault tilgjengelig for målgruppeinnsikt på nytt.
