---
title: Teams-robot for Dynamics 365 Customer Insights (forhåndsversjon)
description: Slå opp enhetlige kundeprofiler i Microsoft Teams ved hjelp av en robot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195854"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams-robot for Dynamics 365 Customer Insights (forhåndsversjon)

Koble til Microsoft Teams for å la en robot slå opp enhetlige kundeprofiler i Teams-kanaler.

:::image type="content" source="media/teams-bot.png" alt-text="Teams-robot som viser en kundeoppføring":::

## <a name="prerequisites"></a>Forutsetning

- Minst én [datakilde lagt til](data-sources.md).
- [Samlingsprosessen](data-unification.md) er fullført.
- Felter er lagt til i [søke- og filterindeksen](search-filter-index.md).
- Customer Insights og Teams er i samme organisasjon.
- Miljøet har primær målgruppe satt til individuelle kunder. Forretningskontoer støttes ikke.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfigurere roboten

1. Gå til **Administrator** > **Tilkoblinger**.
1. Velg **Konfigurer** på Microsoft Teams-flisen.
1. Du blir omdirigert til **Apper**-området i Teams. Du kan også åpne Teams og velge **Apper** nederst i venstre hjørne eller [hente det fra AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) direkte.
1. Søk etter **Customer Insights** og velg appen.
1. Velg **Legg til**.
1. Logg på to Customer Insights i Teams. Det vises en velkomstmelding.

## <a name="things-you-can-do-with-the-bot"></a>Ting du kan gjøre med roboten

Roboten har oppslagsfunksjoner for enhetlige kundeprofiler.

- Skriv inn **søk** etterfulgt av et navn, en e-postadresse eller et annet felt i den enhetlige kundeprofilen som legges til i søke- og filterindeksen.

  Du får et kort med opptil 15 felt fra den resulterende kundeprofilen. Flere treff returnerer en liste over resultater der du kan velge en profil. Du kan finne et nøyaktig treff ved å legge til søkeord i doble anførselstegn.

- Hvis organisasjonen din vedlikeholder flere Customer Insights-miljøer i den samme organisasjonen, angir du **switchinstance** for å velge hvilket miljø du vil koble den til.

- Angi **hjelp** for å vise en liste over tilgjengelige kommandoer for roboten.  

[!INCLUDE [footer-include](includes/footer-banner.md)]