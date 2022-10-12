---
title: Oversikt over prediksjoner
description: Prediksjonsscenarioer og -alternativer som dekkes av Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610202"
---
# <a name="predictions-overview"></a>Oversikt over prediksjoner

Dynamics 365 Customer Insights leveres med en rekke alternativer som bruker kunstig intelligens og maskinlæring til å forutsi data.

## <a name="out-of-box-models"></a>Bruksklare modeller

Den enkleste måten å begynne å forutsi data på er med forhåndsdefinerte modeller, som ofte kalles bruksklare modeller. De krever bare visse data og en viss struktur for å generere innsikt raskt. Følgende modeller er tilgjengelige:

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

- [Kundens levetidsverdi](predict-customer-lifetime-value.md): Forutsier den potensielle omsetningen fra en kunde gjennom hele samhandlingen med en virksomhet.
- [Produktanbefaling](predict-product-recommendation.md): Foreslår sett med prediktive produktanbefalinger basert på kjøpsatferd og kunder med lignende kjøpsmønstre.
- [Abonnementsfrafall](predict-subscription-churn.md): Forutsier om en kunde er i faresonen for ikke lenger å bruke selskapets abonnementsprodukter eller -tjenester.
- [Transaksjonsfrafall](predict-transactional-churn.md): Forutsier om en enkeltkunde ikke lenger vil kjøpe produktene eller tjenestene dine innen et bestemt tidsramme.
- [Sentimentanalyse](sentiment-analysis.md): Analyserer sentiment i tilbakemelding fra kunder og identifiserer forretningsaspekter som ofte blir nevnt.

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

- [Transaksjonsfrafall](predict-transactional-churn.md): Forutsier om en kundeforretningsforbindelse ikke lenger vil kjøpe produktene eller tjenestene dine innen en bestemt tidsramme.

---

> [!TIP]
> Vi anbefaler at du oppdaterer standardmodeller jevnlig med oppdaterte data for å sikre at de informerer virksomhetens brukssak nøyaktig. Data oppdateres ad hoc når nye eller oppdaterte datakilder brukes i systemet. Modellene vil imidlertid bare endre poengsummen i dette tilfellet og fortsette å bruke de eksisterende opplæringsdataene.
>
> Konfigurer en **Oppdateringsplan** ved å angi tidsplanen for ny opplæring av modellen under konfigurasjon. Modellen beholder og endrer poengsummen for denne tidsplanen, noe som du kan endre når som helst.

## <a name="azure-machine-learning-integration"></a>Integrering med Azure Machine Learning

Hvis en organisasjon allerede bruker maskinlæringsscenarioer basert på eksperimenter med Azure Machine Learning, bidrar funksjonen for egendefinerte modeller i Customer Insights til å skape et helhetlig bilde. Opprett arbeidsflyter som hjelper deg å velge dataene du vil generere innsikt fra, og tilordne resultatene til de enhetlige kundeprofilene. Hvis du vil ha mer informasjon, kan du se [Egendefinerte maskinlæringsmodeller](custom-models.md).

## <a name="manage-existing-predictions"></a>Behandle eksisterende prediksjoner

Gå til siden **Intelligens** > **Prediksjoner**. I fanen **Mine prediksjoner** viser du prediksjonene du har opprettet, prediksjonstypen deres, navn på utdataenhet, status, sist gang prediksjonen ble redigert, og sist gang dataene ble oppdatert. Du kan sortere listen over prediksjoner etter enhver kolonne.

Velg en prediksjon for å vise tilgjengelige handlinger.

:::image type="content" source="media/predictions.png" alt-text="Siden Mine prediksjoner.":::

- **Rediger** prediksjonen for å endre egenskapene.
- [**Oppdater**](#refresh-a-prediction) prediksjonen slik at den inneholder de nyeste dataene.
- **Vis** prediksjonsdetaljene.
- [**Brukbarhetsrapport for inndata**](#view-the-input-data-usability-report) for å vise feil, advarsler og anbefalinger.
- **Slett** prediksjonen.

### <a name="refresh-a-prediction"></a>Oppdatere en prediksjon

Prediksjoner kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov. Hvis du vil oppdatere alle prediksjoner manuelt, velger du **Oppdater alle**. Hvis du vil oppdatere en prediksjon, velger du den og deretter **Oppdater**. Hvis du vil [planlegge en automatisk oppdatering](schedule-refresh.md), går du til **Administrator** > **System** > **Plan**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Vise brukbarhetsrapporten for inndata

Brukbarhetsrapporten for inndata gir en konsolidert visning av feilene og advarslene som de bruksklare prediksjonene kan generere. Den gir også anbefalinger om hvordan du kan forbedre modellytelsen.

Rapporten er tilgjengelig etter at en modell har fullført opplæringsprosessen. Den opprettes for hver modell separat, uavhengig av om opplæringen ble fullført eller ikke.

I fanen **Mine prediksjoner** velger du prediksjonen og deretter **Brukbarhetsrapport for inndata**. Eller velg **Brukbarhetsrapport for inndata** fra visningen for prediksjonsdetaljer.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Eksempel på en brukbarhetsrapport for inndata som viser en tabell med feil, advarsler og anbefalinger.":::

Rapporten omfatter følgende:

- **Navn**: Beskrivende navn på feilen, advarselen eller anbefalingen.
- **Trinn**: Modellfasen (Lær opp eller Poengsum) som informasjonen refererer til.
- **Tilstand:** Alvorsgraden til informasjonen (feil, advarsel, anbefaling).
- **Kolonnenavn:** Kolonne i en enhet som må endres for at modellytelsen skal bli bedre.
- **Enhetsnavn:** Navnet på enheten som må endres for at modellytelsen skal bli bedre.
- **Detaljer:** Detaljer om feilen, advarselen eller anbefalingen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
