---
title: Legg til kode på nettstedet
description: Slik legger du til en kodesnutt for å registrere hendelser på nettstedet ditt.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035106"
---
# <a name="install-the-code-snippet-on-a-website"></a>Installer kodesnutten på et nettsted

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Denne artikkelen beskriver hvordan en administrator installerer kodesnutten på et nettstedet. Du vil se hendelser i arbeidsområdet kort tid etter at du har lagt til skriptet på nettstedet. Hvis du vil ha mer informasjon, kan du se [Administrer arbeidsområder og miljøer](manage-environments-workspaces.md). Hvis du vil registrere hendelser i mobilapper, kan du se [Oversikt over utviklerressurser](developer-resources.md).


### <a name="prerequisites"></a>Forutsetninger

* Du må ha administratortillatelser for arbeidsområdet for å lagre dataene.
* Nettstedet eller prosjektet må være driftet på nettet for å sende aktivitetsdata. Data som sendes fra en lokal fil, blir ikke godtatt av serveren.


## <a name="add-code-to-your-website"></a>Legg til kode på nettstedet
1.  Gå til **Administrator** > **Arbeidsområde** og velg **Installasjonsveiledning**.
1. Velg **Kopier kode** for å kopiere kodesnutten. Inntaksnøkkelen for arbeidsområdet er som standard innebygd i kodesnutten.
:::image type="content" source="media/copy-code.png" alt-text="Skjermbilde av kodesnuttsiden.":::
3. Legg til den kopierte kodesnutten på nettstedet, i nærheten av <head> -koden og foran andre skripter eller CSS-koder.
4.  Publiser det oppdaterte nettstedet, og vent noen minutter på å registrere den innkommende nettrafikken.
5.  Hvis du vil vise dataene, velger du arbeidsområdet fra arbeidsområdebytteren i navigasjonsruten. Velg deretter en av rapportene i **Oppdag**-delen.

## <a name="configuration-options"></a>Konfigurasjonsalternativer

Du kan endre følgende konfigurasjonsalternativer i kodesnutten:

- **ingestionKey**: Inntaksnøkkelen som brukes til å sende hendelser til arbeidsområdet. Du kan endre inntaksnøkkelen for å sende hendelser til et annet arbeidsområde. En inntaksnøkkel er unik for hvert arbeidsområde. 
- **autoCapture**: Angir om sidevisninger og samhandlinger med nettstedet skal registreres. Den har to alternativer:
    - **view**: Sett til *true* for å registrere sidevisninger. Sidevisninger registreres som *visnings[hendelser](glossary.md#event)*, en type [basishendelse](glossary.md#base-event).
    - **click** : Sett til *true* for å registrere besøkendes samhandlinger på nettstedet. Samhandlinger registreres som *handlings[hendelser](glossary.md#event)*, en type [basishendelse](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
