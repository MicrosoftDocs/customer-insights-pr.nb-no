---
title: Avanserte nett-SDK-scenarioer
description: Avanserte scenarioer du bør vurdere når du instrumenterer nettstedet med en SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227210"
---
# <a name="advanced-web-sdk-instrumentation"></a>Avansert nett-SDK-instrumentering

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Denne artikkelen veileder deg gjennom avanserte scenarioer du må vurdere når du [instrumenterer nettstedet ditt](instrument-website.md) med en SDK for Dynamics 365 Customer Insights-engasjementsinnsiktsfunksjonalitet.

## <a name="setting-user-details-for-your-event"></a>Angi brukerdetaljer for hendelsen

Med SDK-en kan du definere brukerinformasjon som kan sendes med hver hendelse. Du kan angi brukerdetaljene i en egenskap kalt `user` (de forventede dataene for denne egenskapen er `IUser`-objektet), som ligner `src`, `name` og `cfg` i kodesnuttkonfigurasjonen.

`IUser`-objektet inneholder følgende strengegenskaper:

- **localId**: Brukerens lokale ID.
- **authId**: Den godkjente bruker-ID-en.
- **authType**: Godkjenningstypen som brukes til å hente den godkjente bruker-ID-en.
- **name**: Brukerens navn.
- **email**: Brukerens e-postadresse.

Eksemplet nedenfor viser en kodesnutt som sender brukerinformasjon. Der du ser funksjoner med et stjernesymbol * foran, erstatter du funksjonen med den egendefinerte implementeringen:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Du kan også angi brukerinformasjon ved å kalle opp `setUser(user: IUser)`-API-en. Telemetri som sendes etter oppkall til `setUser`-API-en, inneholder brukerinformasjonen.

## <a name="adding-custom-properties-for-each-event"></a>Legge til egendefinerte egenskaper for hver hendelse

Med SDK-en kan du angi egendefinerte egenskaper som kan sendes med hver hendelse. Du kan angi de egendefinerte egenskapene som et objekt som inneholder nøkkelverdipar (verdien kan være av typen `string | number | boolean`). Du kan legge til objektet i en egenskap som kalles, `props`, som ligner `src`, `name` og `cfg` i kodesnuttkonfigurasjonen.

Eksemplet nedenfor viser en kodesnutt som sender egendefinerte egenskaper:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Du kan også angi egendefinerte egenskaper individuelt ved å kalle opp `setProperty(name: string, value: string | number | boolean)`-API-en.

## <a name="sending-custom-events"></a>Sende egendefinerte hendelser

Du kan bruke SDK-en til å sende egendefinerte hendelser. Du må angi et navn for hendelsen og egenskapene som skal sendes sammen med hendelsen.

Eksemplet nedenfor viser en kodesnutt som sporer en egendefinert hendelse. NAME er verdien i `name`-nøkkelen i snuttkonfigurasjonen. Det er også variabelnavnet i vindusobjektet der SDK-en lastes inn.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
