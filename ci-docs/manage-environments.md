---
title: 'Veiledning: administrer miljøer'
description: Lær hvordan du administrerer eksisterende Customer Insights-miljøer som administrator.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fc3b3f404cf0ac84c782778414494289c803babe
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081673"
---
# <a name="how-to-manage-environments"></a>Veiledning: administrer miljøer

Administratorer [oppretter](create-environment.md) og administrerer miljøer. De kan endre enkelte innstillinger i eksisterende miljøer. Forretning, type, område, lagringsalternativ og Dataverse-innstillinger er faste etter at miljøet er opprettet. Hvis du vil endre disse innstillingene, tilbakestiller du miljøet eller oppretter et nytt miljø.

## <a name="edit-an-existing-environment"></a>Redigere et eksisterende miljø

Du kan redigere noen av detaljene i eksisterende miljøer.

1. Velg **Miljø**-velgeren i overskriften i appen.

1. Velg **Rediger**-ikonet.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikon for å redigere miljøinnstillingene.":::

1. I **Rediger miljø**-boksen kan du oppdatere miljøinnstillingene.

Hvis du vil starte med et nytt miljø, kan du se [Opprett et nytt miljø](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Endre eieren av et miljø

Flere brukere kan ha administratortillatelser, men bare én bruker er eieren av et miljø. Som standard er det administratoren som oppretter et miljø til å begynne med. Som administrator for et miljø kan du tilordne eierskap til en annen bruker med administratortillatelser.

1. Velg **Miljø**-velgeren i overskriften i appen.

1. Velg **Rediger**-ikonet.

1. Gå til trinnet **Grunnleggende informasjon** i boksen **Rediger miljø**.

1. Velg den nye eieren av miljøet i feltet **Endre eier av miljø**-feltet.  

1. Velg **Se gjennom og fullfør**, og **Oppdater** for å ta i bruk endringene.

## <a name="claim-ownership-of-an-environment"></a>Kreve eierskap for et miljø

Hvis brukerkontoen til eieren slettes eller sperres, har ikke miljøet noen eier. Hver administratorbruker kan kreve eierskap og bli ny eier. De kan fortsette å eie miljøet eller [endre eierskapet til en annen administrator](#change-the-owner-of-an-environment).

Hvis du vil kreve eierskap , velger du **Ta eierskap**-knappen som vises øverst på hver side i Customer Insights når den opprinnelige eieren sluttet i organisasjonen.

## <a name="reset-an-existing-environment-preview"></a>Tilbakestill et eksisterende miljø (forhåndsversjon)

Som eier av et miljø kan du tilbakestille et miljø til en tom tilstand hvis du vil slette alle konfigurasjoner og fjerne de innlagte dataene.

1. Velg **Miljø**-velgeren i overskriften i appen.

1. Velg miljøet du vil tilbakestille, og velg den loddrette ellipsen (&vellip;).

1. Velg **Tilbakestill**-alternativet.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontroll for å tilbakestille et miljø.":::

1. Velg om du vil tilbakestille hele miljøet, alt unntatt datakildene, eller alt som er konfigurert oppå unified customer profile.

1. Angi miljønavnet og velg **Tilbakestill** for å bekrefte.

## <a name="delete-an-existing-environment"></a>Slette et eksisterende miljø

Som eier av et miljø kan du slette et miljø du administrerer.

1. Velg **Miljø**-velgeren i overskriften i appen.

1. Velg miljøet du vil tilbakestille, og velg den loddrette ellipsen (&vellip;). 

1. Velg **Slett**-alternativet.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontroll for å slette miljøet.":::

1. Bekreft slettingen ved å angi miljønavnet og velge **Slett**.

> [!IMPORTANT]
> Hvis du sletter et miljø, fjernes ikke tilkoblingen til et Dataverse-miljø. Hvis du planlegger å koble det samme Dataverse-miljøet til et nytt Customer Insights-miljø i fremtiden, må du fjerne denne tilkoblingen. Lær hvordan du [fjerner en eksisterende tilkobling til et Dataverse-miljø](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
