---
title: Vise og opprette måledata
description: Hvordan du oppretter, redigerer og sletter måledata.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034281"
---
# <a name="view-and-create-metrics"></a>Vise og opprette måledata

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Måledata gjør det enklere å forstå atferden til de besøkende. De samler hendelsesegenskaper og måler statistikk og ytelse for nettegenskapene.  

La oss si at du kjører en markedsføringskampanje på nettstedet ditt. Du kan bruke måledata til å spore antall unike besøkende eller brukere som kom til nettstedet ditt under kampanjen. Analyse av måledata gjør det enklere å forstå målgruppen for nettstedet ditt. Hvis du kombinerer måledata med [dimensjoner](dimensions.md) i en [egendefinert rapport](custom-reports.md) kan du måle atferden for å forstå brukerne. Du kan for eksempel dele inn besøkende i kategorier for å skille nye fra returnerende besøkende og finne forskjellene i interesser og hensikt mellom gruppene.

## <a name="view-metrics"></a>Vise måledata

Engasjementsinnsikt omfatter vanlig brukte aggregasjoner av hendelsesegenskaper som systemmåledata: 

- Besøkende
- Besøk
- Sidevisninger
- Klikk

Disse systemmåledataene er basert på eksisterende hendelsesegenskaper i basishendelser.

1. Gå til **Data** i venstre navigasjonsrute. 
1. Velg **Måledata**-fanen for å vise en liste over alle måledata i arbeidsområdet. 
   > [!NOTE]
   > Systemgenererte måledata er skrivebeskyttet. Du kan ikke endre eller slette dem. Du kan bare opprette og redigere egendefinerte måledata.

## <a name="create-a-metric"></a>Opprette en måleverdi

Administratorer for miljø og arbeidsområde kan opprette måledata. Hendelsesegenskaper må sendes til arbeidsområdet før du kan opprette en måleverdi. Du kan opprette måledata basert på hendelsesegenskaper som sendes av basishendelser, eller bruke nett-SDK-en til å [sende egendefinerte hendelsesegenskaper](advanced-SDK-implementation.md).

1. Gå til **Data** > **Måledata**.
1. Velg **Ny måleverdi**.

   :::image type="content" source="media/new-metric.png" alt-text="Legg til en måleverdi i en hendelse.":::

1. For format velger du datatypen **Heltall** eller **Dobbel**. Heltall er et heltall. For Dobbel kan du velge mellom én og tre desimaler.
1. Finn hendelsesegenskapen du vil basere måleverdien på, i **Ressursbibliotek**-ruten.
1. Velg **plusstegnet (+)** ved siden av egenskapen for å bruke den i formelen. Du kan bare opprette en formel basert på én egenskap. 
1. Velg én av følgende mengdefunksjoner. 

   - Sum: den aritmetiske summen av alle verdier 
   - Gjennomsnitt: gjennomsnittet av alle verdier
   - Antall: totalt antall verdier
   - Spesifikt antall: totalt antall unike verdier

   Når du har definert måleverdien, kan du se en aktivitetsforhåndsvisning av måleverdien for den siste timen.

1. Velg **Lagre**. 
1. Skriv inn et navn for måleverdien, og velg **Lagre**.

Det kan ta opptil ett minutt før måleverdien kan brukes til å [opprette egendefinerte rapporter](custom-reports.md).

## <a name="edit-a-metric"></a>Redigere en måleverdi

1. Gå til **Data** > **Måledata**.
1. Velg måleverdien i listen.
1. Endre definisjonen av måleverdien
1. Velg **Lagre**.

## <a name="change-the-name-of-a-metric"></a>Endre navnet på en måleverdi

1. Gå til **Data** > **Måledata**.
1. Velg **Mer [...]** for en måleverdi, og velg **Rediger navn**.
1. Endre navnet. 
1. Velg **Gi nytt navn**.

## <a name="delete-a-metric"></a>Slette en måleverdi

1. Gå til **Data** > **Måledata**.
1. Velg **Mer [...]** for en måleverdi, og velg **Slett**.

   :::image type="content" source="media/delete-metric.png" alt-text="Slett en måleverdi fra en hendelse.":::

1. Velg **Slett** for å bekrefte slettingen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
