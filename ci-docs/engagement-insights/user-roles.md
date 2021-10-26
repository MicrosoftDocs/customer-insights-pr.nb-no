---
title: Roller og tillatelser
description: Oversikt over tilgjengelige roller og tillatelser for arbeidsområdemedlemmer.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645549"
---
# <a name="roles-and-permissions"></a>Roller og tillatelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Et arbeidsområde er en sted der du kan lagre og administrere hendelser og rapporter. Hvis du vil ha mer informasjon, kan du se [Opprette et arbeidsområde og legge til medlemmer](create-workspace.md). 

Et arbeidsområde kan inneholde følgende roller og tillatelser:

- *Medlem*-roller er brukere som har tilgang til et arbeidsområde. Du kan tilordne medlemmer til arbeidsområdet og definere deres roller og tillatelser. 
- *Administrator*-roller administrerer arbeidsområder og miljøer og konfigurerer engasjementsinnsikt for andre brukere. 
- *Bidragsyter*-roller er rettet mot analytikere som ikke trenger å konfigurere engasjementinnsikt, men som vil opprette sine egne rapporter, trakter eller segmenter.

## <a name="permissions"></a>Tillatelser
  
Tabellen nedenfor viser tillatelser for hver rolle. 

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
