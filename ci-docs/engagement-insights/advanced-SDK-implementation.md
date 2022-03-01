---
title: Avanserte nett-SDK-scenarioer
description: Avanserte scenarioer du bør vurdere når du instrumenterer nettstedet med en SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036340"
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
    
Eksemplet nedenfor viser en kodesnutt som sender brukerinformasjon. Der du ser Funksjoner angitt med *, erstatter du den med implementeringen av kall til disse verdiene:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
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

Du kan også angi brukerinformasjon ved å kalle `setUser(user: IUser)`-API-en på SDK-en. Telemetri som sendes etter kall til `setUser API`, inneholder brukerinformasjonen.

## <a name="adding-custom-properties-for-each-event"></a>Legge til egendefinerte egenskaper for hver hendelse

Med SDK-en kan du angi egendefinerte egenskaper som kan sendes med hver hendelse. Du kan angi de egendefinerte egenskapene som et objekt som inneholder nøkkelverdipar (verdien kan være av typen `string | number | boolean`). Objektet kan legges til i en egenskap som kalles `props`, som ligner `src`, `name` og `cfg` i kodesnuttkonfigurasjonen. 

Eksemplet nedenfor viser en kodesnutt som sender egendefinerte egenskaper:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
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

Du kan også angi egendefinerte egenskaper individuelt ved å kalle `setProperty(name: string, value: string | number | boolean)`-API-en på SDK-en.

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