---
title: Roller og tillatelser
description: Oversikt over tilgjengelige roller og tillatelser for arbeidsområdemedlemmer.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036705"
---
# <a name="roles-and-permissions"></a>Roller og tillatelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Et arbeidsområde er hvordan du lagrer og administrerer hendelser og rapporter. Et medlem er en bruker som har tilgang til et arbeidsområde. Du kan tilordne medlemmer til arbeidsområdet og definere deres roller og tillatelser. Administratorroller administrerer arbeidsområder og miljøer og konfigurerer engasjementsinnsikt for andre brukere. De bidragsyterrollene er rettet mot analytikere som ikke trenger å konfigurere engasjementsinnsikt, men som ønsker å lage sine egne rapporter, trakter eller segmenter.

## <a name="permissions"></a>Tillatelser
  
Diagrammet nedenfor viser tillatelser for hver rolle. 

| Tillatelse | Miljøadministrator | Administrator for arbeidsområde | Miljøbidragsyter | Bidragsyter for arbeidsområde | 
|--|--|--|--|--|
| Opprett miljøer (oppretteren blir automatisk miljøadministrator) | X* | X* | X* | X* |  
| Konfigurer miljø (miljømedlemmer, slett miljø) | X |  |  |  |  
| Opprett arbeidsområder | X |  |  |  |  
| Konfigurer arbeidsområder (arbeidsområdemedlemmer, slette arbeidsområde) | X | X |  |  |  
| Konfigurer hendelser og begrensede hendelser | X | X | |  |  
| Vis arbeidsområdehendelser og begrensede hendelser | X | X | |  |  
| Vis arbeidsområderessurser (rapporter, segmenter og måleverdi)| X | X | X | X |  
| Opprett egendefinerte rapporter og trakter | X | X | X | X |  
| Opprett basismåledata og dimensjoner| X | X |  |  |  
| Opprett segmenter| X | X | X | X |  

*Kan bare opprette prøveversjonsmiljøer i forhåndsversjon. 

## <a name="add-members"></a>Legg til medlemmer

Du kan legge til og fjerne medlemmer fra arbeidsområder og miljøer. Hvis du vil ha mer informasjon, kan du se [Miljøer og arbeidsområder](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
