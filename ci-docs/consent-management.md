---
title: Bruk kundesamtykke
description: Overhold kundenes samtykkeinnstillinger i Customer Insights ved å importere samtykkedata.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947504"
---
# <a name="use-customer-consent"></a>Bruk kundesamtykke

Forskrifter for databeskyttelse og personvern gir enkeltpersoner rett til å styre hvordan en organisasjon bruker personopplysningene. Eksempler på slike forskrifter er EUs personvernforordning (GDPR) eller California Consumer Privacy Act i USA. Disse forskriftene gjør det mulig for brukere å velge bort at personopplysningene samles inn, behandles av eller deles med tredjeparter.  

Kunder kan velge å trekke tilbake eller holde tilbake samtykket for bestemte kontaktformer. Kunder kan også be deg om at du velger dem bort fra innsamling, lagring, bruk eller salg av personopplysninger. Det er viktig at organisasjonen din overholder alle kunders samtykke- og personverninnstillinger.  

Dynamics 365 Customer Insights hjelper deg med å overholde kundenes forespørsler ved å importere og lagre innstillingene deres som en del av de enhetlige kundeprofilene.

Hvis samtykkedata lagres atskilt fra kundeprofilene, [legger du til samtykkedataene som en ny datakilde](#import-and-unify-consent-data). Datakilden som inneholder samtykkedataene, blir lagt til i datasamslingsprosessen. En vellykket samling av samtykkedata og kundeprofiler fører deretter til enhetlige kundeprofiler som inneholder samtykkeinformasjonen. For kundeprofiler som allerede inneholder samtykkeinformasjon, går du direkte til delen [bruk samtykkedata](#use-consent-data).

## <a name="prerequisites"></a>Forutsetning

Følgende informasjon må være tilgjengelig i kildedataene for å samle samtykkedata med andre kundeprofiler:

- Alternativ nøkkel for å tildele samtykkeinformasjonen til brukerprofiler i Customer Insights. Det kan for eksempel være et telefonnummer eller en e-postadresse.
- Samtykkeverdi for å fastslå statusen til kundens samtykke.

Vurder å legge til følgende *valgfrie* informasjon:

- Primærnøkkel for å oppdatere statusen for samtykke hvis en kunde ber om en endring.
- Samtykketype hvis det finnes mer enn én måte å behandle kundeinformasjon på.
- Dato for samtykke eller andre typer data som er relevante for samtykkescenarioene.

Eksempeltabell for en enkel samtykkedatabase med flere alternativer for samtykke:

|Samtykke-ID (primærnøkkel)   |E-post (alternativ nøkkel)  |Samtykkealternativ  |Samtykkeverdi  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Nyhetsbrev       |  False       |
|2    |  holly@contoso.com       |  Produktoppdateringer       |  True       |
|3    |  frank@contoso.com       |  Nyhetsbrev       | True        |
|4    |  frank@contoso.com       |  Produktoppdateringer       |  False       |

## <a name="import-and-unify-consent-data"></a>Importer og samle samtykkedata

Du kan importere samtykkedata på samme måte som du innhenter andre datakilder til Customer Insights på. Hvis du vil ha mer informasjon om støttede datakilder og hvordan du importerer dem, kan du se [Oversikt over datakilder](data-sources.md).

Hvis du vil ha mer informasjon om hvordan du samler datakildene, kan du se [Oversikt over datasamling](data-unification.md).

## <a name="use-consent-data"></a>Bruke samtykkedata

Når samtykkedataene dine er en del av de enhetlige kundeprofilene, kan du bruke dem i Customer Insights. Opprett for eksempel et segment med en regel for å sikre at du overholder kundenes personvern- og personverninnstillinger. Regler som støtter samtykkeinnstillinger, brukes til å utelate brukere fra et segment basert på profilattributter. Legg en regel i et segment som utelater kundeprofiler som ikke ga samtykke til kontakt.

Ved å henvise til eksempeltabellen ovenfor kan et segment inneholde denne regelen: `Consent option=Newsletter & Consent value=True`. Denne konfigurasjonen resulterer i et segment som overholder til kontaktinnstillinger for å sende et nyhetsbrev.

Hvis du vil ha mer informasjon om hvordan du bygger segmenter, kan du se [Opprett segmenter](segment-builder.md).

Når segmentet er opprettet, kan du bruke et av de mange [eksportalternativene](export-destinations.md) til å bruke segmentet i andre programmer.

## <a name="ensure-updated-consent-status"></a>Sikre oppdatert samtykkestatus

Det er viktig at du holder samtykkestatusen for kundene oppdatert. Den planlagte oppdateringen i Customer Insights importerer alltid den nyeste tilstanden til datakildene. Denne informasjonen behandles deretter gjennom datasamling og fører til oppdaterte kundeprofiler. Disse oppdaterte profilene brukes deretter til å oppdatere segmenter for å sikre at du arbeider med den mest oppdaterte informasjonen.

Sørg med andre ord for at kildedataene som blir importert til Customer Insights, alltid har den nyeste informasjonen.

Hvis du vil ha mer informasjon, kan du se [Oppdater segmenter manuelt](segments.md#refresh-segments) eller [Konfigurer en planlagt oppdatering](system.md#schedule-tab).
