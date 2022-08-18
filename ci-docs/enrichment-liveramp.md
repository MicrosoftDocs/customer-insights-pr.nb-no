---
title: Forbedre kundeprofiler med identitetsdata fra LiveRamp (forhåndsversjon)
description: Supplere kundeprofiler med LiveRamp-data.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237824"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Forbedre kundeprofiler med identitetsdata fra LiveRamp (forhåndsversjon)

LiveRamp gir deterministiske frakoblede identitetsløsning og konsolidering av kundedata. Du kan tilordne personlige identifikatorer i kundedataene til AbiliTec-identitetsgrafen og motta AbiliTec-ID-er. Deretter kan du bruke disse IDene til bedre forening av kundedataene.

## <a name="supported-countriesregions"></a>Støttede land/områder

Vi støtter for øyeblikket bare supplering av kundeprofiler med LiveRamp-data i USA.

## <a name="prerequisites"></a>Forutsetning

- Et aktivt LiveRamp-abonnement. Hvis du vil ha et abonnement, kontakter du LiveRamp-kontoteamet ditt eller [dynamics@liveramp.com](mailto:dynamics@liveramp.com)for mer informasjon.

- Et aktivt AbiliTec-abonnement med en klient-ID og hemmelig for tilgang til API-en. Hvis du vil ha mer informasjon, kan du se [API-utviklerhub for AbiliTec](https://developers.liveramp.com/abilitec-api/).

- En LiveRamp-[tilkobling](connections.md) er [konfigurert](#configure-the-connection-for-liveramp) av en administrator.

## <a name="configure-the-connection-for-liveramp"></a>Konfigurere tilkoblingen for LiveRamp

Du må være en [administrator](permissions.md#admin) i Customer Insights og ha en aktiv LiveRamp-klient-ID og -hemmelighet.

1. Velg **Legg til tilkobling** når du konfigurerer en supplering, eller gå til **Administrator** > **Tilkoblinger**, og velg **Konfigurer** på LiveRamp-flisen.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurasjonsrute for å konfigurere tilkoblingen til LiveRamp AbiliTec-tjenesten. ":::

1. Skriv inn et navn på tilkoblingen og en gyldig LiveRamp-klient-ID og en hemmelighet.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Bekreft** for å validere konfigurasjonen, og velg deretter **Lagre**.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på flisen **Identitet** fra LiveRamp-flisen.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitetsflis på oversiktssiden for supplering. ":::

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Velg tilkoblingen. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Velg **Neste**.

1. Velg **Kundedatasett** og velg profilen eller segmentet du vil supplere med identitetsdata fra LiveRamp. *Kunde*-enheten supplerer alle kundeprofilene dine, mens segmentsuppleringer bare supplerer kundeprofiler i det segmentet.

1. Definer hvilken type felter fra de enhetlige profilene som skal brukes for samsvarende identitetsdata fra LiveRamp. Minst et av feltene **Navn og adresse**, **E-post** eller **Telefon** er nødvendig. Hvis du vil ha høyere samsvarsnøyaktighet, legger du til andre felter. Velg **Neste**.

1. Tildel feltene til identifikasjonsdataene fra LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Alternativer for datatilordning for LiveRamp-supplering.":::

1. Velg **Neste** for å fullføre felttilordningen.

1. Angi et **Navn** for suppleringen og **Utdataenhetsnavn**.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

1. Velg **Kjør** for å starte suppleringsprosessen, eller lukk for å gå tilbake til siden **Suppleringer**.

## <a name="view-enrichment-results"></a>Vis suppleringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antall kunder supplert av feltet** gir en neddrilling i dekningen av hvert supplerte felt.

## <a name="next-steps"></a>Neste trinn

Bygg på toppen av de supplerte kundedataene. Bruk AbiliTec-IDene til å konsolidere kundeprofiler i en personbasert visning.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
