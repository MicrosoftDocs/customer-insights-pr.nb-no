---
title: Kjøre iOS SDK-eksemplet
description: Eksempel på prosjekt for å lære om iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036840"
---
# <a name="run-the-ios-sdk-sample"></a>Kjøre iOS SDK-eksemplet

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dette iOS-eksempelprosjektet hjelper deg med å forstå hvordan SDK fungerer i en app. Du behøver ikke å skrive kode. Bare legg til inkluderingssnøkkelen, og du kan se hendelser i arbeidsområdet med en gang.

## <a name="prerequisites"></a>Forutsetninger

- [Xcode-versjon 9+](https://developer.apple.com/xcode/downloads/)
- [Inkluderingsnøkkel](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Laste ned iOS SDK-eksemplet

1. [Last ned iOS SDK-eksempelet for engasjementsinnsikt](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Pakk ut den komprimerte filen `ei-ios-sample.zip`.
1. Åpne eksempelapprosjektet i Xcode.
1. I `EIConfig.plist`-filen erstatter du strengen `“YOUR-INGESTION-KEY”` i feltet `ingestionKey` med inkluderingsnøkkelen for arbeidsområdet fra Engasjementinnsikt under **Admin** > **Arbeidsområde** > **Installasjonsveiledning**.
1. Velg **Kjør** for å starte eksempelprosjektet.
1. Vise hendelsene i arbeidsområdet.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
