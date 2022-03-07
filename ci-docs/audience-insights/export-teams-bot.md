---
title: Robot for Microsoft Teams
description: Slå opp enhetlige kundeprofiler i Microsoft Teams ved hjelp av en robot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406524"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams-robot for Dynamics 365 Customer Insights (forhåndsversjon)

Koble til Microsoft Teams for å la en robot slå opp enhetlige kundeprofiler i Teams-kanaler.

> [!div class="mx-imgBorder"]
> ![Teams-robot som viser en kundeoppføring](media/teams-bot.png "Teams-robot som viser en kundeoppføring")

## <a name="prerequisites"></a>Forutsetninger

Når du skal konfigurere roboten, må følgende forhåndskrav være oppfylt:

- Det er minst én [datakilde lagt til](data-sources.md).
- [Samlingsprosessen](data-unification.md) er fullført.
- Felt er lagt til i [søke- og filterindeksen](search-filter-index.md).
- Customer Insights og Teams er i samme organisasjon.

## <a name="configure-the-bot"></a>Konfigurere roboten

1. I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.
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
