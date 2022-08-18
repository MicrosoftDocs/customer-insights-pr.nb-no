---
title: Administrere prediksjoner
description: Finn ut hvordan du administrerer, feilsøker og forbedrer prediksjoner.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 42abfb305efaccaeef48e32f2cc69f3d36fbe73d
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245477"
---
# <a name="manage-predictions"></a>Administrere prediksjoner

Denne artikkelen tar for seg noen oppgaver som de fleste prediksjonsscenarioene har til felles.

## <a name="troubleshoot-a-failed-prediction"></a>Feilsøke en mislykket prognose

1. Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.

1. Velg de loddrette ellipsene ved siden av prediksjonen du vil vise feillogger for.

1. Velg **Logger**.

1. Se gjennom alle feilene. Det finnes flere typer feil som kan oppstå, og de beskriver hvilken betingelse som forårsaket feilen. En feil på grunn av at det ikke er nok data til å forutsi nøyaktig, blir vanligvis løst ved å laste inn flere data i Customer Insights.

## <a name="input-data-usability-report"></a>Brukbarhetsrapport for inndata

Brukbarhetsrapporten for inndata gir en konsolidert visning av feilene og advarslene som de bruksklare prediksjonene kan generere. Den gir også anbefalinger om hvordan du kan forbedre modellytelsen.

Rapporten er tilgjengelig etter at en modell har fullført opplæringsprosessen. Den opprettes for hver modell separat, uavhengig av om den ble fullført eller ikke.

### <a name="view-the-input-data-usability-report"></a>Vise brukbarhetsrapporten for inndata

Etter at en bruksklar modell har fullført opplæringstrinnet, kan du vise rapporten:
- Velg ellipsen ved siden av modellnavnet, og velg **Brukbarhetsrapport for inndata**.
- Velg statusen for en modell, og velg **Vis brukbarhetsrapport for inndata** i sideruten.
- Velg en av modellene i listen, og velg **Brukbarhetsrapport for inndata** på kommandolinjen.
- Åpne siden over modellresultater, og velg **Brukbarhetsrapport for inndata** på kommandolinjen.

### <a name="information-in-the-input-data-usability-report"></a>Informasjon i brukbarhetsrapporten for inndata

Følgende kolonner i rapporten inneholder nyttig informasjon for å forbedre dataene for modellen.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Eksempel på en brukbarhetsrapport for inndata som viser en tabell med feil, advarsler og anbefalinger.":::

- **Navn**: Beskrivende navn på feilen, advarselen eller anbefalingen.
- **Trinn**: Modellfasen (Lær opp eller Poengsum) som informasjonen refererer til.
- **Tilstand:** Alvorsgraden til informasjonen (feil, advarsel, anbefaling).
- **Kolonnenavn:** Kolonne i en enhet som må endres for at modellytelsen skal bli bedre.
- **Enhetsnavn:** Navnet på enheten som må endres for at modellytelsen skal bli bedre.
- **Detaljer:** Detaljer om feilen, advarselen eller anbefalingen.

## <a name="refresh-a-prediction"></a>Oppdatere en prediksjon

Prognoser oppdateres automatisk på samme [tidsplan som dataene dine oppdateres](schedule-refresh.md), som konfigurert i innstillingene. Du kan også oppdatere dem manuelt.

1. Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.

1. Velg de loddrette ellipsene ved siden av den forutsigelsen du vil oppdatere.

1. Velg **Oppdater**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Slette en prediksjon

Sletting av en prognose fjerner også utdataenheten.

1. Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.

1. Velg de loddrette ellipsene ved siden av den forutsigelsen du vil slette.

1. Velg **Slett**.
