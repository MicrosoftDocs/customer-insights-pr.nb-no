---
title: Opprett nytt miljø
description: Formålet med et miljø og hvordan du oppretter et nytt.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f82ff588c2ffbe82c3ee7df2498ac2cca2bad31
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225441"
---
# <a name="create-a-new-environment"></a>Opprett nytt miljø 

## <a name="overview"></a>Oversikt

Et miljø er et sted der du administrerer arbeidsområder og tilkoblinger. Hvordan du bruker miljøer avhenger av organisasjonen og brukssaken. Du kan for eksempel opprette:

- Et enkeltstående miljø.
- Separate miljøer for test og produksjon.
- Separate miljøer for bestemte team eller avdelinger i organisasjonen som inneholder relevante hendelser for hver målgruppe.
- Separate miljøer for forskjellige globale filialer av firmaet.
- Tilkoblinger til Customer Insights-målgruppeinnsiktfunksjon.

## <a name="create-a-new-environment"></a>Opprett nytt miljø

1. Velg miljøvelgeren til høyre i hovedbanneret, og klikk deretter **+Ny**.

   :::image type="content" source="media/environment-picker.png" alt-text="Velg miljøvelgeren.":::

1. Skriv inn et **Miljønavn** i **Installasjon**-ruten.

1. Velg **Type** forretningsforbindelse, avhengig av plantype.

1. Velg **Område**, og velg **Neste**. 

1. Skriv inn et **Navn på arbeidsområde**, som gjør det mulig å samle inn data for bestemte nettsteder eller apper. Hvis du vil ha mer informasjon, kan du se [Opprette en arbeidsområde](create-workspace.md).

1. Velg **Arbeidsområdetype** (web eller mobil) du vil opprette. 

1. Velg **Vis avanserte innstillinger** for å aktivere eller deaktivere disse valgfrie innstillingene:

   - Aktiver/deaktiver **Fra ukjent til kjent** for å knytte webhendelser til brukere som tidligere har godkjent. Hvis du vil ha mer informasjon, kan du se [Gjenkjenne webhendelser fra tidligere godkjente besøkende](unknown-to-known.md).
   - Aktiver/deaktiver **Filtrer robottrafikk** til "aktivert" for å fjerne webtrafikk med roboter for dette arbeidsområdet. 

1. Velg **Fullfør** når du er ferdig. 

1. Installer kodesnutten for å begynne å motta data, og velg deretter **Fullfør** for å opprette arbeidsområdet. Hvis du vil ha mer informasjon, kan du se [Oversikt over utviklerressurser](developer-resources.md).

> [!NOTE]
> Du kan nå legge til medlemmer og tilordne tilgangsnivået fra **Rolle**-listen. Hvis du vil ha mer informasjon, kan du se [Roller og tillatelser](user-roles.md). 

Hvis du vil ha mer informasjon, kan du se [Administrer miljøer og arbeidsområder](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Arbeide med det nye miljøet

- [Opprett et arbeidsområde](../engagement-insights/create-workspace.md) og legg til medlemmer.
- [Legg til kode på nettstedet](../engagement-insights/instrument-website.md) eller [mobilappen](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Vise en [rapport i sanntid](../engagement-insights/view-reports.md)  eller opprette [egendefinerte rapporter](../engagement-insights/custom-reports.md).
- [Opprett begrensede hendelser](../engagement-insights/refined-events.md) for eksport.
- [Eksporter dataene](../engagement-insights/export-events.md) til Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
