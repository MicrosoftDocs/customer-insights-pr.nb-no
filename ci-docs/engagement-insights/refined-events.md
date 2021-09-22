---
title: Opprett og endre finjusterte hendelser
description: Slik oppretter og endrer du begrensede hendelser.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034786"
---
# <a name="create-and-modify-refined-events"></a>Opprett og endre finjusterte hendelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


En hendelse er data som representerer brukeratferd, for eksempel aktivitet på et nettsted.

- En *basishendelse* registrerer når en bruker viser en side (visningshendelse) eller samhandler med innhold (handlingshendelse).
- En *begrenset* hendelse er en virtuell visning av en basishendelse. Du definerer begrensede hendelser ved å fjerne og legge til egenskaper eller ved å filtrere hendelser basert på egenskapsverdier.

Bruk begrensede hendelser for å redusere omfanget for en basishendelse for [eksport](export-events.md) eller til å fjerne egenskaper som ikke er nødvendig for eksport.

## <a name="create-refined-events"></a>Opprette finjusterte hendelser

Du kan opprette en begrenset hendelse fra en basishendelse på tre måter. 

1. Gå til **Data**> **Hendelse** og velg et av følgende alternativer:
    - Velg **Nye hendelser**, og velg deretter **Opprett begrensede hendelser**.
    - Velg en basishendelse for å åpne en detaljert visning, og velg **Opprett begrensede hendelser** fra toppmenyen.
    - Velg **Mer [...]** for å åpne hurtigmenyen for en basishendelse. Velg deretter **Opprett begrensede hendelser**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Alternativer for å opprette begrensede hendelser.":::

1. Angi følgende informasjon i dialogboksen **Opprett begrensede hendelser**:

- Velg en hendelse i rullegardinlisten **Basishendelser** hvis du oppretter en ny hendelse.
- Angi et navn i boksen **Visningsnavn for begrensede hendelser**.
- Du kan eventuelt oppdatere det foreslåtte **faktiske navnet** uten å bruke mellomrom.

3. Velg **Opprett** for å bruke innstillingene.

1. I den detaljerte visningen av den begrensede hendelsen velger du **Legg til og fjern egenskaper** for å åpne ruten **Rediger egenskap**. 

1. Bruk avmerkingsboksene til å velge egenskapene du vil vise, og de du vil skjule. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Rediger egenskaper for begrensede hendelser.":::

1. Velg **Bekreft** for å ta i bruk valget.

1. Velg **Lagre** for å lagre konfigurasjonen.

## <a name="edit-refined-events"></a>Rediger begrensede hendelser

Du kan endre navnet og egenskapene for en begrenset hendelse.

### <a name="edit-event-name"></a>Rediger hendelsesnavn

1. Gå til **Data** > **Hendelser**. 
1. Velg **Mer [...]** for en hendelse, og velg **Rediger navn**.
1. Oppdater hendelsesnavnet og velg **Gi nytt navn**.

### <a name="edit-selected-properties"></a>Rediger valgte egenskaper

1. Gå til **Data** > **Hendelser**, og velg de begrensede hendelsene for å åpne den detaljerte visningen.
1. Velg **Legg til og fjern egenskaper**. 
1. Rediger merkingen av avmerkingsboksene.
1. Velg **Bekreft** og deretter **Lagre** for å ta i bruk endringene.

Hvis du vil ha mer informasjon om eksport av hendelser, kan du se [Eksporter hendelser](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
