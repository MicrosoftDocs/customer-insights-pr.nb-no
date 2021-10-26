---
title: Opprett nytt arbeidsområde
description: Formålet med et arbeidsområde og hvordan du oppretter et nytt.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 816f948331a06794c15000eb779f93cc7fdda202
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645322"
---
# <a name="create-a-new-workspace-and-add-members"></a>Opprette et nytt arbeidsområde og legge til medlemmer

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Et arbeidsområde er hvordan du kan vise brukeraktivitet i sanntid for å få en bedre forståelse av målgruppen. Det er her du lagrer og administrerer hendelser og rapporter.

Når du oppretter et arbeidsområde, velger du datatypen du vil fokusere på. Du kan når som helst legge til andre brukere, eller medlemmer, i et eksisterende arbeidsområde. 

## <a name="create-a-new-workspace"></a>Opprett nytt arbeidsområde

Prosessen med å opprette et arbeidsområde omfatter konfigurasjon av *miljøet* for å organisere arbeidsområdet. Et miljø er plass som kan inneholde ett eller flere arbeidsområder. Du kan bruke et miljø til å administrere arbeidsområdene og tilkoblingene til Customer Insights-målgruppeinnsiktfunksjonen.

1. Velg **Nytt** fra arbeidsområdebytteren.

   :::image type="content" source="media/new-workspace.png" alt-text="Kundeinnsikt-siden med bildeforklaring i navigasjonsruten og beskrivelse.":::

1. Angi et **navn på arbeidsområde** i **Arbeidsområde**-ruten.

   :::image type="content" source="media/workspace-name.png" alt-text="Angi et arbeidsområdenavn.":::

1. Velg plattformtypen (web eller mobil) du vil måle.

1. Velg **Vis avanserte innstillinger** for å aktivere eller deaktivere disse valgfrie innstillingene:

   - Aktiver/deaktiver **Fra ukjent til kjent** for å knytte webhendelser til brukere som tidligere har godkjent. Hvis du vil ha mer informasjon, kan du se [Gjenkjenne webhendelser fra tidligere godkjente besøkende](unknown-to-known.md)
   - Aktiver/deaktiver **Filtrer robottrafikk** til "aktivert" for å fjerne webtrafikk med roboter for dette arbeidsområdet. 

1. Velg **Fullfør** når du er ferdig. 

1. Installer kodesnutten for å begynne å motta data, og velg deretter **Fullfør** for å opprette arbeidsområdet. Hvis du vil ha mer informasjon, kan du se [Oversikt over utviklerressurser](developer-resources.md).

> [!NOTE]
> Du kan nå legge til medlemmer og tilordne tilgangsnivået fra **Rolle**-listen. Hvis du vil ha mer informasjon, kan du se [Roller og tillatelser](user-roles.md). 

Hvis du vil ha mer informasjon, kan du se [Administrer miljøer og arbeidsområder](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
