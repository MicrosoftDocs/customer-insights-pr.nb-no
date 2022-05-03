---
title: Robot for Microsoft Teams
description: Slå opp enhetlige kundeprofiler i Microsoft Teams ved hjelp av en robot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 89a293d5b6f9f5452b2ccba495d2475002806019
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647426"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams-robot for Dynamics 365 Customer Insights (forhåndsversjon)

Koble til Microsoft Teams for å la en robot slå opp enhetlige kundeprofiler i Teams-kanaler.

> [!div class="mx-imgBorder"]
> ![Teams-robot som viser en kundeoppføring.](media/teams-bot.png "Teams-robot som viser en kundeoppføring")

## <a name="prerequisites"></a>Forutsetninger

Når du skal konfigurere roboten, må følgende forhåndskrav være oppfylt:

- Det er minst én [datakilde lagt til](data-sources.md).
- [Samlingsprosessen](data-unification.md) er fullført.
- Felt er lagt til i [søke- og filterindeksen](search-filter-index.md).
- Customer Insights og Teams er i samme organisasjon.
- Miljøet har primær målgruppe satt til individuelle kunder. Forretningskontoer støttes ikke.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfigurere roboten

1. Gå til **Administrator** > **Eksporter mål**.
1. Velg **Konfigurer** på Microsoft Teams-flisen.
1. Du blir omdirigert til **Apper**-området i Teams. Du kan også åpne Teams og velge **Apper** nederst i venstre hjørne eller [hente det fra AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) direkte.
1. Søk etter **Customer Insights** og velg appen.
1. Velg **Legg til**.
1. Etter at du har logget på Customer Insights i Teams, vil du se en velkomstmelding og kan komme i gang.

## <a name="things-you-can-do-with-the-bot"></a>Ting du kan gjøre med roboten

Roboten har oppslagsfunksjoner for enhetlige kundeprofiler.

- Skriv inn **søk** etterfulgt av et navn, en e-postadresse eller et annet felt i den enhetlige kundeprofilen som legges til i søke- og filterindeksen.

  Du får et kort med opptil 15 felt fra den resulterende kundeprofilen. Flere treff returnerer en liste over resultater der du kan velge en profil. Du kan legge til søkeord i doble anførselstegn for å finne et nøyaktig treff.

- Hvis organisasjonen din vedlikeholder flere Customer Insights-miljøer i den samme organisasjonen, kan du angi **switchinstance** for å velge hvilket miljø du vil koble den til.

- Angi **hjelp** for å vise en liste over tilgjengelige kommandoer for roboten.  


[!INCLUDE [footer-include](includes/footer-banner.md)]