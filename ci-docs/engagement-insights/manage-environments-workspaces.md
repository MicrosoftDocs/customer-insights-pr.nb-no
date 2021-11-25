---
title: Administrer arbeidsområder og miljøer
description: Slik oppretter du, gir nytt navn til og sletter arbeidsområder og miljøer.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 09cb3ddf0f8b4507b7eae6668ea3dad08cfcea29
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673809"
---
# <a name="manage-environments-and-workspaces"></a>Administrere miljøer og arbeidsområder

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Oversikt

Dette emnet beskriver hvordan du behandler arbeidsområder og miljøer når de allerede er opprettet. 

- Et *arbeidsområde* er en sted der du kan lagre og administrere hendelser og rapporter. Det er her du kan vise brukeraktivitet i sanntid. Når du oppretter et arbeidsområde, velger du datatypen du vil sende til arbeidsområdet. For øyeblikket støttes webdata og mobilapper. Hvis du vil ha mer informasjon, kan du se [Opprette et nytt arbeidsområde og legge til medlemmer](create-workspace.md).

- Et *miljø* er et sted der du administrerer arbeidsområder og tilkoblinger. Hvis du vil ha mer informasjon, kan du se [Opprette et nytt miljø](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Administrere et eksisterende arbeidsområde

Du kan vedlikeholde flere arbeidsområder samtidig i et miljø. Din [rolle](user-roles.md) avgjør hvordan du kan arbeide i dem. 

 - Du må være miljøadministrator eller arbeidsområdeadministrator for å kunne administrere arbeidsområdet.
 - Som arbeidsområdeadministrator kan du gi nytt navn til eksisterende arbeidsområder eller slette dem. 

:::image type="content" source="media/workspace-edit.png" alt-text="Administrasjonssenter for arbeidsområde.":::

### <a name="edit-a-workspace-name"></a>Rediger et navn på arbeidsområde

1. Gå til **Administrator** > **Arbeidsområde** og velg **Innstillinger**.

1. Angi et nytt navn i boksen **Navn på arbeidsområde**.

1. Velg **Lagre** for å ta i bruk endringene.

### <a name="delete-a-workspace"></a>Slett et arbeidsområde

Hvis du sletter arbeidsområdet, fjernes alt innhold, data, innstillinger og tillatelser permanent. Det kan ikke angres.

1. Gå til **Administrator** > **Arbeidsområde** og velg **Innstillinger**.

1. Velg **Slett arbeidsområde**. 

1. I dialogboksen **Slett arbeidsområde** angir du **BEKREFT SLETTING**. 

1. Velg **Slett** for å slette arbeidsområdet permanent.

### <a name="manage-workspace-members"></a>Administrere medlemmer i arbeidsområde

1. Gå til **Administrator** > **Arbeidsområde** og velg **Medlemmer**.

1. Velg **Legg til medlemmer** for å gi tilgang til og [tilordne roller](user-roles.md). For øyeblikket er bare **arbeidsområdeadministrator** tilgjengelig.

1. Velg **Legg til medlemmer** for å legge dem til i arbeidsområdet.

## <a name="manage-an-existing-environment"></a>Administrere et eksisterende miljø

Som miljøadministrator kan du få tilgang til et miljø fra den venstre navigasjonsruten. Du kan konfigurere miljøinnstillinger, andre miljøadministratorer og arbeidsområder. Velg faner for å gå mellom ulike områder i administrasjonssenteret.

:::image type="content" source="media/environment-edit.png" alt-text="Administrasjonssenter for miljø.":::

### <a name="edit-an-environment-name"></a>Redigere et miljønavn

1. Gå til **Administrator** > **Miljø** og velg **Innstillinger**.

1. Oppdater **miljønavnet** og velg **Lagre** for å ta i bruk endringene.

### <a name="delete-an-environment"></a>Slette et miljø

Miljøadministratorer kan slette miljøer. Før du kan slette et miljø, må du fjerne alle arbeidsområder under det.

1. Gå til **Administrator** > **Miljø** og velg **Innstillinger**.

1. Velg **Slett miljø**. 

1. I dialogboksen **Slett arbeidsområde** angir du **BEKREFT SLETTING**. 

1. Velg **Slett** for å slette miljøet permanent.

### <a name="manage-environment-members"></a>Administrer miljømedlemmer

1. Gå til **Administrator** > **Miljø** og velg **Medlemmer**.

1. Velg **Legg til medlemmer** for å oppdatere medlemmer og [tilordne roller](user-roles.md). For øyeblikket er bare **miljøadministrator** tilgjengelig.

1. Velg **Legg til medlemmer** for å legge dem til i miljøet.

## <a name="manage-connections"></a>Administrer tilkoblinger

Ved å opprette målgruppeinnsikt kan du vise rapporter i engasjementsinnsikt basert på enhetlige kundeprofiler. 

Hvis du vil ha mer informasjon, kan du se [Opprett en kobling mellom målgruppeinnsikt og engasjementsinnsikt](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Administrer personopplysninger

Du kan beskytte kundens personlige opplysninger ved å slette eller eksportere identifiserbare data for sluttbrukeren.

Hvis du vil ha mer informasjon, kan du se [Slett og eksporter hendelsesdata som inneholder personlige opplysninger](../dsr-rights-requests.md#deleting-and-exporting-event-data-containing-end-user-identifiable-information).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
