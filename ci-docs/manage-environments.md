---
title: Behandle miljøer
description: Lær hvordan du administrerer eksisterende Customer Insights-miljøer som administrator.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304298"
---
# <a name="manage-environments"></a>Behandle miljøer

Administratorer [oppretter](create-environment.md) og administrerer miljøer. De kan endre enkelte innstillinger i eksisterende miljøer. Forretning, type, område, lagringsalternativ og Dataverse-innstillinger er faste etter at miljøet er opprettet. Hvis du vil endre disse innstillingene, [tilbakestiller du miljøet](#reset-an-existing-environment-preview) eller [oppretter et nytt miljø](create-environment.md).

## <a name="edit-an-existing-environment"></a>Redigere et eksisterende miljø

Rediger detaljer for et eksisterende miljø, for eksempel navnet eller angivelse av standardmiljøet.

1. Velg **Miljø**-velgeren i overskriften i appen.

1. Velg **Rediger**-ikonet.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikon for å redigere miljøinnstillingene.":::

1. I **Rediger miljø**-ruten oppdaterer du miljøinnstillingene.

1. Velg **Se gjennom og fullfør**, og **Oppdater** for å ta i bruk endringene.

## <a name="change-the-owner-of-an-environment"></a>Endre eieren av et miljø

Flere brukere kan ha administratortillatelser, men bare én bruker er eieren av et miljø. Som standard er det administratoren som oppretter et miljø til å begynne med. Som administrator for et miljø kan du tilordne eierskap til en annen bruker med administratortillatelser.

1. Velg **Miljø**-velgeren i overskriften i appen.

1. Velg **Rediger**-ikonet.

1. Gå til trinnet **Grunnleggende informasjon** i ruten **Rediger miljø**.

1. Velg den nye eieren av miljøet i feltet **Endre eier av miljø**-feltet.  

1. Velg **Se gjennom og fullfør**, og **Oppdater** for å ta i bruk endringene.

## <a name="claim-ownership-of-an-environment"></a>Kreve eierskap for et miljø

Hvis brukerkontoen til eieren slettes eller sperres, har ikke miljøet noen eier. Enhver administratorbruker kan kreve eierskap og bli ny eier. Eieradministratoren kan fortsette å eie miljøet eller [overføre eierskapet til en annen administrator](#change-the-owner-of-an-environment).

Hvis du vil kreve eierskap , velger du **Ta eierskap**-knappen som vises øverst på hver side i Customer Insights når den opprinnelige eieren sluttet i organisasjonen.

## <a name="reset-an-existing-environment-preview"></a>Tilbakestill et eksisterende miljø (forhåndsversjon)

Som eier av et miljø tilbakestiller du et miljø til en tom tilstand hvis du vil slette alle konfigurasjoner og fjerne de innlagte dataene.

1. Velg **Miljø**-velgeren i overskriften i appen.

1. Velg miljøet du vil tilbakestille, og velg den loddrette ellipsen (&vellip;).

1. Velg **Tilbakestill (forhåndsversjon)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontroll for å tilbakestille et miljø.":::

1. Velg om du vil tilbakestille hele miljøet, alt unntatt datakildene, eller alt som er konfigurert oppå unified customer profile.

1. Angi miljønavnet og velg **Tilbakestill** for å bekrefte.

## <a name="delete-an-existing-environment"></a>Slette et eksisterende miljø

Som eier av et miljø kan du slette det.

> [!IMPORTANT]
> Hvis du sletter et miljø, fjernes ikke tilkoblingen til et Dataverse-miljø. Hvis du planlegger å koble det samme Dataverse-miljøet til et nytt Customer Insights-miljø i fremtiden, må du [fjerne denne tilkoblingen til Dataverse-miljøet](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Velg **Miljø**-velgeren i overskriften i appen.

1. Velg miljøet du vil slette, og velg den loddrette ellipsen (&vellip;). 

1. Velg **Slett**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontroll for å slette miljøet.":::

1. Bekreft slettingen ved å angi miljønavnet og velge **Slett**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
