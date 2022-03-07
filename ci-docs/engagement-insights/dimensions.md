---
title: Vise og opprette dimensjoner
description: Hvordan du oppretter, redigerer og sletter dimensjoner.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034009"
---
# <a name="view-and-create-dimensions"></a>Vise og opprette dimensjoner

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En dimensjon er et attributt for en hendelse som kan beskrive, filtrere eller gruppere data. Hvis du kjører en markedsføringskampanje på nettstedet, kan du bruke dimensjoner til å sortere besøkende etter nye og returnerende brukere.  

Engasjementsinnsikt omfatter bruksklare dimensjoner for hendelsesegenskaper. Eksempler:

- Nettlesernavn
- Sidenavn
- Enhetsmodell
- Operativsystem
- Land

## <a name="view-dimensions"></a>Vis dimensjoner

Dimensjoner er basert på eksisterende hendelsesegenskaper. Når du bruker sporingskoden for engasjementsinnsikt, opprettes systemdimensjoner automatisk.

1. Gå til **Data** i venstre navigasjonsrute. 
1. Velg **Dimensjoner** for å vise en liste over alle dimensjonene i arbeidsområdet. 
   > [!NOTE]
   > Systemgenererte dimensjoner er skrivebeskyttet. Du kan ikke redigere dem. Du kan bare opprette og redigere egendefinerte dimensjoner.

## <a name="create-a-dimension"></a>Opprett dimensjon

Miljø- og arbeidsområdeadministratorer kan opprette egendefinerte dimensjoner i tillegg til systemgenererte dimensjoner. Egendefinerte dimensjoner er basert på standardegenskaper for basishendelser, eller de kan bruke [egendefinerte egenskaper for en hendelse](advanced-SDK-implementation.md).

1. Gå til **Data** > **Dimensjoner**.
1. Velg **Legg til dimensjon**.

   :::image type="content" source="media/add-dimension.png" alt-text="Legg til en dimensjon for en hendelse.":::

1. Velg en egenskap du vil basere dimensjonen på, i ruten **Opprett dimensjon**. Listen over egenskaper viser alle egenskapene i arbeidsområdet som ikke er tilordnet til en dimensjon.
1. Angi et navn i **Visningsnavn**-boksen. Du kan eventuelt legge til en beskrivelse.
1. Velg **Opprett** for å lagre dimensjonen. Det kan ta opptil ett minutt før du kan bruke dimensjonen i en [egendefinert rapport](custom-reports.md) eller et [segment](segments.md). 

## <a name="edit-a-dimension"></a>Redigere en dimensjon

Du kan endre navnet på og beskrivelsen av en dimensjon.

1. Gå til **Data** > **Dimensjoner**.
1. Velg dimensjonen du vil slette.
1. Oppdater dimensjonen i ruten **Rediger dimensjon**.
1. Velg **Bruk** for å lagre endringene.

## <a name="delete-a-dimension"></a>Slette en dimensjon

Du kan bare slette brukeropprettede dimensjoner, så du kan ikke fjerne systemdimensjoner.

Når du sletter en dimensjon, slettes den permanent. Rapporter og segmenter som bruker en slettet dimensjon, fungerer ikke lenger. 

1. Gå til **Data** > **Dimensjoner**.
1. Velg dimensjonen du vil slette.
1. Velg **Slett dimensjon** i ruten **Rediger dimensjon**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Slett en dimensjon for en hendelse.":::

1. Angi **BEKREFT SLETTING** (med store bokstaver) for å bekrefte slettingen. 
1. Velg **Slett**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
