---
title: Hurtigstart for produktinnføring
description: Førstegangsopplevelse for å konfigurere engasjementsinnsiktfunksjoner.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/05/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: eebe51d343f6afbed52a66c52ab6a60eb5cd410367fb2e4409eb8679f357c91e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033919"
---
# <a name="first-run-experience"></a>Opplevelse av førstegangskjøring

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med engasjementsinnsikt, en funksjonen i Dynamics 365 Customer Insights, kan du samle inn og måle kundeatferd på nettstedet ditt. Denne artikkelen forklarer hvordan du registrerer deg for engasjementsinnsikt, konfigurerer et arbeidsområde, legger til medlemmer i det og gjør endringer.

## <a name="sign-up-for-a-demo-of-engagement-insights"></a>Registrere deg for en demonstrasjon av engasjementsinnsikt

Du må ha en aktiv Microsoft Azure Active Directory-brukerkonto. 

1. Åpne nettstedet for [engasjementsinnsikt](https://pi.dynamics.com/). 

1. Logg på med skole- eller jobbkontoen din.

1. Velg området ditt, og bruk avmerkingsboksen til å angi om du vil velge å motta oppdateringer og tilbud via e-post.

1. Se gjennom **vilkårene for bruk for engasjementsinnsikt (forhåndsversjon)** og **personvernerklæringen**, og velg deretter **Utforsk demo** for å godta dem.

1. Utforsk produktet ved hjelp av et sett med eksempeldata. 

## <a name="set-up-your-first-workspace-in-engagement-insights"></a>Konfigurer det første arbeidsområdet i engasjementsinnsikt

Et arbeidsområde er hvordan du lagrer og administrerer hendelser og rapporter.

Slik oppretter du ditt første arbeidsområde

1. Velg **Koble til dataene** for å starte veiviseren i engasjementsinnsikt. 

:::image type="content" source="media/banner.png" alt-text="Customer Insights-siden med Koble til data-knappen.":::

2. Velg aktivitetstypen du vil måle i et nytt arbeidsområde. For øyeblikket er bare **nettstedsaktivitet** tilgjengelig. **Appaktivitet** og **Enhetsaktivitet** blir tilgjengelige i fremtidige versjoner.

1. Velg **Neste** for å bekrefte og opprette arbeidsområdet.

1. Legg til kodesnutten på nettstedet for å begynne å motta data i engasjementsinnsikt. Du kan implementere dette med en gang eller dele koden og instruksjonene med nettstedsadministratoren. Hvis du vil finne kodesnutten senere, kan du gå til **Administrator** > **Arbeidsområde** > **Installasjonsveiledning**.

   > [!IMPORTANT]
   > Data vises ikke i arbeidsområdet før koden er implementert på nettstedet.

1. Velg **Fullført** for å åpne det nye arbeidsområdet. 

## <a name="add-members-to-an-existing-workspace"></a>Legg til medlemmer i et eksisterende arbeidsområde

Som standard har bare personen som opprettet arbeidsområdet, tilgang til det. Du kan når som helst legge til andre brukere fra organisasjonen, i et eksisterende arbeidsområde.

:::image type="content" source="media/add-members.png" alt-text="Medlemmer-siden med bildeforklaring på Legg til medlemmer-knappen.":::

1. Gå til **Administrator** > **Arbeidsområde** > **Medlemmer**.

2. Velg **Legg til medlemmer**. Bruk **Medlemmer**-boksen til å legge til andre personer i organisasjonen. Du kan legge til flere medlemmer samtidig.

3. Velg en **rolle** som skal tilordnes de nye medlemmene. For øyeblikket er **arbeidsområdeadministrator** det eneste tilgjengelige valget. Andre roller blir lagt til i fremtidige versjoner.

4. Velg **Legg til medlemmer** for å bekrefte.

Hvis du vil fjerne medlemmer fra et arbeidsområde, velger du **...** ved siden av navnene deres på **Medlemmer**-siden, og deretter velger du **Slett** på rullegardinmenyen.

## <a name="edit-a-workspace"></a>Rediger et arbeidsområde

Du kan når som helst redigere detaljene for eksisterende arbeidsområder.

:::image type="content" source="media/change-workspace-settings.png" alt-text="Siden Innstillinger for arbeidsområde med arbeidsområde på navn og beskrivelse for arbeidsområde.":::

1. Gå til **Administrator** > **Arbeidsområde** > **Innstillinger**.

1. Endre **navnet** på arbeidsområdet.

1. Velg **Lagre** for å ta i bruk endringene.

## <a name="add-another-new-workspace"></a>Legg til et nytt arbeidsområde

:::image type="content" source="media/workspace-switcher.png" alt-text="Kundeinnsikt-siden med bildeforklaring i navigasjonsruten og beskrivelse.":::

Du kan opprette flere arbeidsområder for å klassifisere dataene.

1. Velg **Nytt arbeidsområde** i arbeidsområdevelgeren.

1. Angi et **navn** og eventuelt en **beskrivelse**.

1. Velg **Opprett**.

## <a name="switch-between-workspaces"></a>Bytt mellom arbeidsområder

Hvis du vil bytte mellom arbeidsområder, velger du arbeidsområdebytteren. Du kan også opprette et nytt arbeidsområde, eller velge **Netteksempel** for å vise rapporter og prøve funksjoner ved hjelp av eksempeldata. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]