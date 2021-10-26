---
title: Kjør et eksempel på nett-SDK
description: Finn ut hvordan du tilpasser og kjører et eksempel på nett-SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606249"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Kjør nett-SDK-eksempelet for Dynamics 365 Customer Insights-engasjementsinnsiktfunksjonalitet

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Biblioteket for nett-SDK for engasjementsinnsikt er et JavaScript-bibliotek med eksempelkode som du kan bruke på nettstedet.

## <a name="prerequisites"></a>Forutsetninger

- Installer [Visual Studio Code](https://code.visualstudio.com/).
- [Installer Live Server-utvidelsen](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) i Visual Studio Code, og gjør deg kjent med hvordan du kjører Live Server.
- Du må ha et [arbeidsområde for engasjementsinnsikt](create-workspace.md).

## <a name="run-sample"></a>Kjør eksempel

1. [Last ned eksemplet på nett-SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Pakk ut den komprimerte filen `ei_websdk_sample.zip`.

1. Åpne den utpakkede mappen i Visual Studio Code.

1. Gå til engasjementinnsiktportalen for arbeidsområdet. Velg **Administrator** > **Arbeidsområde** og deretter **Installasjonsveiledning**. Følg det første alternativet, og velg **Kopier kode** for å kopiere JavaScript-kodesnutten.

1. I `ei_websdk_sample.html`-filen limer du inn kodesnutten du nettopp kopierte, under denne linjen:

   - <- LIM INN JAVASCRIPT-KODESNUTT FRA ENGASJEMENTINNSIKTSPORTALEN HER UNDER DENNE LINJEN – >

1. Åpne `ei_websdk_sample.html`-filen ved hjelp av Live Server i Visual Studio Code ved å velge **Bli tilkoblet** fra statuslinjen.

1. En visningshendelse sendes åpnes automatisk når siden åpnes. Hvis du klikker på en av knappene på siden, sendes handlingshendelser. **Spor hendelser**-knappen sender også egendefinerte hendelser. Når du velger **Gå til Bing**-knappen, sendes en handlingshendelse før du navigerer til Bing-nettstedet.

1. Se på hendelser som flyter når du navigerer til arbeidsområdet. Dette arbeidsområdet er knyttet til inntaksnøkkelen som ble angitt i trinn 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
