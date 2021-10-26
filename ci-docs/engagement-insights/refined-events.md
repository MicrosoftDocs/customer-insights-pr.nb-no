---
title: Opprett og endre hendelser
description: Opprette og endre hendelser.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606247"
---
# <a name="create-and-modify-events"></a>Opprett og endre hendelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En hendelse er data som representerer brukeratferd, for eksempel aktivitet på et nettsted.

- En *basishendelse* registrerer når en bruker viser en side (visningshendelse) eller samhandler med innhold (handlingshendelse).
- En *begrenset* hendelse er en virtuell visning av en basishendelse. Du definerer begrensede hendelser ved å fjerne og legge til egenskaper eller ved å filtrere hendelser basert på egenskapsverdier.

## <a name="prerequisites"></a>Forutsetninger

Hvis du vil se hendelser, må nettstedsdataene dine først kobles til engasjementsinnsikt med en kodesnutt. Hvis du vil ha mer informasjon, kan du se [Installere web-SDK-en på et webområde](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Koble til dataene dine først.":::

## <a name="create-refined-events"></a>Opprett begrensede hendelser

Bruk begrensede hendelser for å redusere omfanget for en basishendelse for [eksport](export-events.md) eller til å fjerne egenskaper som ikke er nødvendig for eksport.

> [!NOTE]
> Når du har lagt til web-SDK-en på webområdet, kan du vise basishendelsene og opprette begrensede hendelser. 

Slik viser du basishendelsene:

1. Gå til **Data** i venstre navigasjonsrute.

1. Velg **Hendelser** for å vise en liste over alle hendelsene i arbeidsområdet.

    :::image type="content" source="media/data-events.png" alt-text="Vis hendelser.":::

Slik oppretter du en finjustert hendelse fra en basishendelse: 

1. Gå til **Data** > **Hendelser** og velg **+ Nye hendelser** øverst på skjermen.

1. Velg **Opprett begrensede hendelser** i dialogboksen **Nye hendelser**, og velg deretter **Neste**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Veiviser for nye hendelser.":::
     
1. Skriv inn følgende informasjon i dialogboksen **Nye hendelser**.

   - Velg en hendelse fra rullegardinlisten **Basishendelser**.
   - Angi et navn i boksen **Visningsnavn for begrensede hendelser**.
   - Du kan eventuelt oppdatere det foreslåtte **faktiske navnet** uten å bruke mellomrom.

1. Velg **Opprett** for å bruke innstillingene.

Den finjusterte hendelsen vises nå i **Hendelse**-listen.

### <a name="edit-event-name"></a>Rediger hendelsesnavn

Du kan endre navnet og egenskapene for en basishendelse eller finjustert hendelse.

1. Gå til **Data** > **Hendelser**. 

1. Velg **Mer [...]** for en hendelse, og velg **Rediger navn**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Alternativer for å opprette begrensede hendelser.":::

3. Oppdater hendelsesnavnet og velg **Gi nytt navn**.

### <a name="view-the-details-of-a-refined-event"></a>Vise detaljene for en finjustert hendelse:

1. Velg den grunnleggende eller finjusterte hendelsen i listen **Hendelse**. 

1. Velg **Legg til og fjern egenskaper** øverst på skjermen for å åpne ruten **Rediger egenskaper**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Legg til og fjern egenskaper.":::

1. Bruk avmerkingsboksene til å velge egenskapene du vil vise, og de du vil skjule. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Rediger egenskaper for begrensede hendelser.":::

1. Velg **Bekreft** for å ta i bruk valget, og velg deretter **Lagre**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Redigere valgte egenskaper for en finjustert hendelse

1. Gå til **Data** > **Hendelser**, og velg de begrensede hendelsene for å åpne den detaljerte visningen.
1. Velg **Legg til og fjern egenskaper**. 
1. Rediger merkingen av avmerkingsboksene.
1. Velg **Bekreft** og deretter **Lagre** for å ta i bruk endringene.

Hvis du vil ha mer informasjon om eksport av hendelser, kan du se [Eksporter hendelser](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
