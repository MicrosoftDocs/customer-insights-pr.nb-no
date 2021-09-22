---
title: Kjør et eksempel på nett-SDK
description: Finn ut hvordan du tilpasser og kjører et eksempel på nett-SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036615"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Kjør nett-SDK-eksempelet for Dynamics 365 Customer Insights-engasjementsinnsiktfunksjonalitet

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Biblioteket for nett-SDK for engasjementsinnsikt er et JavaScript-bibliotek med eksempelkode som du kan bruke på nettstedet.

## <a name="prerequisites"></a>Forutsetninger

- Installer [Visual Studio Code](https://code.visualstudio.com/).
- [Installer Live Server-utvidelsen](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) i Visual Studio Code, og gjør deg kjent med hvordan du kjører Live Server.
- Du må ha [inntaksnøkkelen](instrument-website.md).

## <a name="run-sample"></a>Kjør eksempel

1. [Last ned eksemplet på nett-SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Pakk ut den komprimerte filen `ei_websdk_sample.zip`.

1. Åpne den utpakkede mappen i Visual Studio Code.

1. Erstatt strengen INGESTION_KEY i `ei_websdk_sample.html`-filen med inntaksnøkkelen fra portalen for engasjementsinnsikt, og strengen NAME med det globale navnet du vil at SDK-en skal startes i. Kontroller at du erstatter alle forekomster.

1. Åpne `ei_websdk_sample.html`-filen ved hjelp av Live Server i Visual Studio Code ved å velge **Bli tilkoblet** fra statuslinjen.

1. En visningshendelse sendes åpnes automatisk når siden åpnes. Hvis du klikker på en av knappene på siden, sendes handlingshendelser. **Spor hendelser**-knappen sender også egendefinerte hendelser. Når du velger **Gå til Bing**-knappen, sendes en handlingshendelse før du navigerer til Bing-nettstedet.

1. Se på hendelser som flyter når du navigerer til arbeidsområdet. Dette arbeidsområdet er knyttet til inntaksnøkkelen som ble angitt i trinn 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]