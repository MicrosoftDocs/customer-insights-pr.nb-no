---
title: Legg til kode på nettstedet
description: Slik legger du til en kodesnutt for å registrere Dynamics 365 Customer Insights-hendelser på nettstedet ditt.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231034"
---
# <a name="install-the-web-sdk-on-a-website"></a>Installer nett-SDK på et nettsted

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Denne artikkelen beskriver hvordan en administrator installerer SDK (Software Development Kit) på et nettsted. Du vil se hendelser i arbeidsområdet kort tid etter at du har instrumentert nettstedet. Hvis du vil ha mer informasjon, kan du se [Administrer arbeidsområder og miljøer](manage-environments-workspaces.md). Hvis du vil registrere hendelser i mobilapper, kan du se [Oversikt over utviklerressurser](developer-resources.md).


### <a name="prerequisites"></a>Forutsetninger

* Du må ha administratortillatelser for arbeidsområdet for å lagre dataene.
* Nettstedet eller prosjektet må være driftet på nettet for å sende aktivitetsdata. Data som sendes fra en lokal fil, blir ikke godtatt av serveren.


## <a name="add-web-sdk-to-your-website"></a>Legg til nett-SDK på nettstedet

Gå til **Administrator** > **Arbeidsområde** og velg **Installasjonsveiledning**. Du kan spore to alternativer for å installere nett-SDK. Den første er å bruke en nedlastingskobling, og den andre er å installere en pakke for Node Package Manager (NMP).

### <a name="option-1-using-the-download-link"></a>Alternativ 1. Bruk av nedlastingskoblingen

1. Velg **Kopier kode** for å kopiere kodesnutten. Inntaksnøkkelen for arbeidsområdet er som standard innebygd i kodesnutten.
  :::image type="content" source="media/copy-code.png" alt-text="Skjermbilde av kodesnuttsiden.":::

1. Legg til den kopierte koden på nettstedet ditt, i nærheten av <head> -koden og foran andre skripter eller CSS-koder.
1. Publiser det oppdaterte nettstedet, og vent noen minutter på å registrere den innkommende nettrafikken.
1. Hvis du vil vise dataene, velger du arbeidsområdet fra arbeidsområdebytteren i navigasjonsruten. Velg deretter en av rapportene i **Oppdag**-delen.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Alternativ 2: Bruk av NPM-pakken (anbefales for JavaScript-baserte nettapper)

1. Gå til [NPM-nettsiden](https://www.npmjs.com/package/engagementinsights-web), og følg instruksjonene for å installere og konfigurere nett-SDK-en for NPM-pakken.
1. Publiser det oppdaterte nettstedet, og vent noen minutter på å registrere den innkommende nettrafikken.
1. Hvis du vil vise dataene, velger du arbeidsområdet fra arbeidsområdebytteren i navigasjonsruten. Velg deretter en av rapportene i **Oppdag**-delen.

## <a name="configuration-options"></a>Konfigurasjonsalternativer

Du kan endre følgende konfigurasjonsalternativer i kodesnutten:

- **ingestionKey**: Inntaksnøkkelen som brukes til å sende hendelser til arbeidsområdet. Du kan endre inntaksnøkkelen for å sende hendelser til et annet arbeidsområde. En inntaksnøkkel er unik for hvert arbeidsområde.
- **autoCapture**: Angir om sidevisninger og samhandlinger med nettstedet skal registreres. Den har to alternativer:
    - **view**: Sett til *true* for å registrere sidevisninger. Sidevisninger registreres som *visnings[hendelser](glossary.md#event)*, en type [basishendelse](glossary.md#base-event).
    - **click** : Sett til *true* for å registrere besøkendes samhandlinger på nettstedet. Samhandlinger registreres som *handlings[hendelser](glossary.md#event)*, en type [basishendelse](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
