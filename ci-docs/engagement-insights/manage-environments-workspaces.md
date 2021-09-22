---
title: Administrer arbeidsområder og miljøer
description: Slik oppretter du, gir nytt navn til og sletter arbeidsområder og miljøer.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034054"
---
# <a name="manage-environments-and-workspaces"></a>Administrere miljøer og arbeidsområder

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Oversikt

Et arbeidsområde er en sted der du kan lagre og administrere hendelser og rapporter. Det er her du kan vise brukeraktivitet i sanntid. Når du oppretter et arbeidsområde, velger du datatypen du vil sende til arbeidsområdet. For øyeblikket støttes webdata og mobilapper.

Et miljø er et sted der du administrerer arbeidsområder og tilkoblinger. Hvordan du bruker miljøer avhenger av organisasjonen og brukssaken. Du kan for eksempel opprette:

-   Et enkeltstående miljø.
-   Separate miljøer for test og produksjon.
-   Separate miljøer for bestemte team eller avdelinger i organisasjonen som inneholder relevante hendelser for hver målgruppe.
-   Separate miljøer for forskjellige globale filialer av firmaet.
-   Tilkoblinger til Customer Insights-målgruppeinnsiktfunksjon.

## <a name="choose-an-environment-and-create-a-workspace"></a>Velg et miljø og opprett et arbeidsområde 

Hvert arbeidsområde må være i et miljø. Du kan velge et eksisterende miljø eller opprette et nytt når du oppretter et arbeidsområde. Deretter kan du velge å legge til arbeidsområdemedlemmer og begynne å samle inn data.

**Slik oppretter du ditt første arbeidsområde**

1. Velg **Nytt** i arbeidsområdebytteren i engasjementsinnsikt. 

   :::image type="content" source="media/New-workspace.png" alt-text="Arbeidsområdevelger for Customer Insights-side.":::

1. Velg et miljø fra listen, eller velg **Opprett nytt miljø**.

1. Angi et navn i **Navn på arbeidsområde**. 

1. Velg hvilken type miljø du vil opprette, avhengig av om du vil måle hva som skjer på et nettsted eller i en mobilapp. 

1. Du kan legge til medlemmer og tilordne tilgangsnivået deres fra **Rolle**-listen. Deretter velger du **Fullfør** for å opprette arbeidsområdet eller **Neste** for å installere kode. 

1. Installer kodesnutten for å begynne å motta data, og velg deretter **Fullført**. 

## <a name="manage-a-workspace"></a>Administrer et arbeidsområde

Du kan vedlikeholde flere arbeidsområder samtidig i et miljø. Din [rolle](user-roles.md) avgjør hvordan du kan arbeide i dem. 

 - Du må være miljøadministrator eller arbeidsområdeadministrator for å kunne administrere arbeidsområdet.
 - Som arbeidsområdeadministrator kan du gi nytt navn til eksisterende arbeidsområder eller slette dem. 

### <a name="edit-a-workspace-name"></a>Rediger et navn på arbeidsområde

1. Gå til **Administrator** > **Arbeidsområde** og velg **Innstillinger**.

1. Angi et nytt navn i boksen **Navn på arbeidsområde**.

1. Velg **Lagre** for å ta i bruk endringene.

### <a name="delete-a-workspace"></a>Slett et arbeidsområde

Hvis du sletter et arbeidsområde, fjernes alt innhold, data, innstillinger og tillatelser permanent. Det kan ikke angres.

1. Gå til **Administrator** > **Arbeidsområde** og velg **Innstillinger**.

1. Velg **Slett arbeidsområde**. 

1. Angi **BEKREFT SLETTING** i dialogen **Slett arbeidsområde**. 

1. Velg **Slett** for å slette arbeidsområdet permanent.

### <a name="manage-workspace-members"></a>Administrere medlemmer i arbeidsområde

1. Gå til **Administrator** > **Arbeidsområde** og velg **Medlemmer**.

1. Velg **Legg til medlemmer** for å gi tilgang til og [tilordne roller](user-roles.md). For øyeblikket er bare **arbeidsområdeadministrator** tilgjengelig.

1. Hvis du konfigurerer en [tilkobling til målgruppeinnsikt](configure-connections.md), kan du velge **Tillat tilgang til profildata** slik at medlemmet kan se rapporter basert på [brukerprofiler](profile-reports.md).

1. Velg **Legg til medlemmer** for å legge dem til i arbeidsområdet.

## <a name="manage-an-environment"></a>Administrere et miljø

Som miljøadministrator kan du få tilgang til et miljø fra den venstre navigasjonsruten. Du kan konfigurere miljøinnstillinger, andre miljøadministratorer, arbeidsområder og [tilkoblinger til målgruppeinnsikt](configure-connections.md). Velg faner for å gå mellom ulike områder i administrasjonssenteret.

:::image type="content" source="media/New-environment.png" alt-text="Administrasjonssenter for miljø.":::

### <a name="create-an-environment"></a>Opprett et miljø

1. Velg **+Ny** i arbeidsområdevelgeren.

1. Åpne rullegardinlisten **Miljø** i den veiledede opplevelsen, og velg **Opprett nytt miljø**. 

1. Oppgi et **miljønavn**.

   :::image type="content" source="media/create-environment.png" alt-text="Trinn i den veiledede opplevelsen for å angi miljødetaljene.":::

1. Velg **Område**, og velg **Neste**. 

1. Angi et navn på arbeidsområdet, og velg hvilken type arbeidsområde du vil opprette. 

1.  Du kan eventuelt legge til medlemmer og kopiere kodesnutt fullføre opprettingsprosessen.

### <a name="rename-an-environment"></a>Endre navn på et miljø

1. Gå til **Administrator** > **Miljø** og velg **Innstillinger**.

1. Oppdater **miljønavnet** og velg **Lagre** for å ta i bruk endringene.

### <a name="manage-environment-members"></a>Administrer miljømedlemmer

1. Gå til **Administrator** > **Miljø** og velg **Medlemmer**.

1. Velg **Legg til medlemmer** for å oppdatere medlemmer og [tilordne roller](user-roles.md). For øyeblikket er bare **miljøadministrator** tilgjengelig.

1. Hvis du konfigurerer en [tilkobling til målgruppeinnsikt](configure-connections.md), kan du velge **Tillat tilgang til profildata** slik at medlemmet kan se rapporter basert på [brukerprofiler](profile-reports.md).

1. Velg **Legg til medlemmer** for å legge dem til i miljøet.

### <a name="delete-an-environment"></a>Slette et miljø

Miljøadministratorer kan slette miljøer. Før du kan slette et miljø, må du fjerne alle arbeidsområder under det.

1. Gå til **Administrator** > **Miljø** og velg **Innstillinger**.

1. Velg **Slett miljø**. 

1. Angi **BEKREFT SLETTING** i dialogen **Slett arbeidsområde**. 

1. Velg **Slett** for å slette miljøet permanent.

## <a name="manage-connections"></a>Administrer tilkoblinger

Ved å opprette målgruppeinnsikt kan du vise rapporter i engasjementsinnsikt basert på enhetlige kundeprofiler. 

Hvis du vil ha mer informasjon, kan du se [Konfigurer tilkoblinger](configure-connections.md).

## <a name="manage-personal-data"></a>Administrer personopplysninger

Du kan beskytte kundens personlige opplysninger ved å slette eller eksportere identifiserbare data for sluttbrukeren.

Hvis du vil ha mer informasjon, kan du se [Slett og eksporter hendelsesdata som inneholder personlige opplysninger](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
