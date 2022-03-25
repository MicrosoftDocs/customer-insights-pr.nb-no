---
title: Supplering av LiveRamp-identifikasjonsdata
description: Supplere kundeprofiler med LiveRamp-data.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373047"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Forbedre kundeprofiler med identitetsdata fra LiveRamp (forhåndsvisning) 

LiveRamp gir deterministiske frakoblede identitetsløsning og konsolidering av kundedata. Du kan tilordne personlige identifikatorer i kundedataene til AbiliTec-identitetsgrafen og motta AbiliTec-ID-er. Deretter kan du bruke disse IDene til bedre forening av kundedataene. 

## <a name="prerequisites"></a>Krav 

Følgende forutsetninger må være oppfylt for at du skal konfigurere suppleringen: 

- Du må ha et aktivt LiveRamp-abonnement. Hvis du vil ha et abonnement, kontakter du LiveRamp-kontoteamet ditt eller [dynamics@liveramp.com](mailto:dynamics@liveramp.com)for mer informasjon.   

- Et aktivt AbiliTec-abonnement med en klient-ID og hemmelig for tilgang til API-en. Hvis du vil ha mer informasjon, kan du se [API-utviklerhub for AbiliTec](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Støttede land/områder 

Vi støtter for øyeblikket bare supplering av kundeprofiler med LiveRamp-data i USA. 

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen 

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen. 

1. Velg **Suppler dataene** på flisen **Identitet**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitetsflis på oversiktssiden for supplering. ":::

1. Velg en [tilkobling](connections.md) fra rullegardinlisten. Kontakt en administrator hvis ingen tilkobling er tilgjengelig. Hvis du er administrator, kan du opprette en tilkobling ved å velge **Legg til tilkobling**. Velg **LiveRamp** fra nedtrekkslisten. 

1. Velg **Neste**, og velg **Kundedatasett** du vil bruke til å supplere med identitetsdata fra LiveRamp. Du kan velge *Kunde*-enheten for å supplere alle kundeprofilene dine, eller velge en *segment*-enhet som bare skal supplere kundeprofiler i det segmentet. 

1. Velg **Neste**, og definer hvilken type felt fra de enhetlige profilene som skal brukes til å se etter samsvarende identitetsdata fra LiveRamp. Minst ett av feltene **Navn og adresse**, **Telefon** eller **E-post** er nødvendig. 

   > [!TIP]
   > Jo flere nøkkelidentifikatorer og felt du tilordner, jo større er sannsynligheten for høyere samsvarsrate 

1. Tilordne feltene fra den enhetlige *Kunde*-enheten som skal brukes til samsvar med LiveRamps AbiliTec ID-graf. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Alternativer for datatilordning for LiveRamp-supplering.":::

1. Velg **Neste** for å fullføre felttilordningen. 

1. Angi et **Navn** for suppleringen og **Utdataenheten**. 

1. Velg **Lagre supplering** etter at du har sett gjennom valgene. 

## <a name="configure-the-connection-for-liveramp"></a>Konfigurere tilkoblingen for LiveRamp 

Du må være en administrator for å [konfigurere tilkoblinger](connections.md). Velg **Legg til tilkobling** når du konfigurerer suppleringen, eller gå til **Administrator** > **Tilkoblinger**, og velg **Konfigurer** på **LiveRamp**-flisen. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurasjonsrute for å konfigurere tilkoblingen til LiveRamp AbiliTec-tjenesten. ":::

1. For **Visningsnavn** angir du navnet for tilkoblingen. 

1. Angi en gyldig LiveRamp-klient-ID og en hemmelighet. 

1. Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**. 

1. Velg **Bekreft** for å validere konfigurasjonen. 

1. Velg **Lagre** for å fullføre tilkoblingen. 

## <a name="enrichment-results"></a>Resultater av supplering 

Hvis du vil starte den omfattende prosessen, velger du Kjør fra kommandolinjen. Du kan også la systemet kjøre supplementet automatisk som en del av en  [planlagt oppdatering](system.md#schedule-tab). Behandlingstiden avhenger av størrelsen på kundedataene. 

Når suppleringsprosessen er fullført, kan du se gjennom de nylig berikede kundeprofildataene under  **Mine suppleringer**. I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler. 

Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge  **Vis supplerte data**. 

## <a name="next-steps"></a>Neste trinn

Bygg på toppen av de supplerte kundedataene. Bruk AbiliTec-IDene til å konsolidere kundeprofiler i en personbasert visning. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar 

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til LiveRamp, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at LiveRamp oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732). Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
