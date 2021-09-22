---
title: Gjenkjenne netthendelser fra tidligere godkjente besøkende med ukjent til kjent
description: Med Ukjent til kjent-funksjonen kan du knytte hendelser på et nettsted til besøkende som er godkjent tidligere.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036795"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Gjenkjenne netthendelser fra tidligere godkjente besøkende

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

**Ukjent til kjent**-funksjonen i engasjementsinnsikt gjør det mulig å knytte hendelser på et nettsted til besøkende som er godkjent tidligere. Hvis funksjonen er deaktivert, identifiseres ikke besøkende som ble godkjent under et tidligere besøk, og deretter dro, identifiseres ikke hvis de ikke godkjennes på nytt når de kommer tilbake. 

En person besøkte for eksempel et nettsted i forrige uke, logget på brukerkontoen sin på nettstedet og bladde gjennom produktkatalogen. Personen kommer tilbake den følgende uken for å bla gjennom flere produkter uten å logge inn på kontoen sin. Områdeeieren som brukte **ukjent til kjent**-funksjonen, vil vite at den samme personen var kommet tilbake og hva de hadde gjort på nettstedet. Dette muliggjør mer presis rapportering og analyse av nettstedsaktiviteter.

## <a name="enable-unknown-to-known"></a>Aktiver ukjent til kjent

Du må vøre [arbeidsområdeadministrator](user-roles.md) for å aktivere denne funksjonen. 

1. I engasjementsinnsikt går du til **Administrator** > **Arbeidsområde**. 
2. Velg fanen **Innstillinger**.
3. I delen **Ukjent til kjent** setter du veksleknappen til **Aktivert**.

![Aktiver ukjent til kjent](media/U2Ktoggle.png "Aktiver ukjent til kjent")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Legg til JavaScript-kode i nettstedets sporingssnutt

Et nettsted kan fange opp **authId for brukere** med følgende JavaScript-eksempel ved hjelp av [nett-SDK-en for engasjementsinnsikt](advanced-SDK-implementation.md). For at **ukjent til kjent**-funksjonen skal fungere må du registrere authId *og* aktivere userMapping:True i JavaScript-snutten som i eksemplet nedenfor.

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
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
