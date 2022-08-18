---
title: Tilpass opplevelsene med data om kjente og ukjente brukere
description: Ta med informasjonen om tidligere ukjente brukere når du kjenner identiteten deres.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224307"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Tilpass opplevelsene med data om kjente og ukjente brukere

Det er ikke noen ny utfordring å administrere kundedata, men det blir stadig vanskeligere etter hvert som brukere navigerer blant de ulike digitale kanalene varemerker tilbyr. En bruker som er kjent (godkjent) i én kanal, blir ukjent (ikke godkjent) i en annen hvis vedkommende ikke er logget på. Problemet er ofte at ikke godkjente (ukjente) brukere ikke har en felles ID. Den kunne ha blitt brukt til å knytte sammen meningsfulle attributter for profiler og generere enhetlige kundeprofiler. Customer Insights bidrar til å løse dette problemet ved å hente inn data fra sporingsmetoder på kildesystemene. Konsolider ukjente og kjente profiler gir organisasjoner en fullstendig visning av oppdaterte profiler og historiske transaksjoner, virkemåte og demografi. Det gir til og med en identitetsløsning som gjør at du kan samle kundeaktivitet på tvers av flere kanaler, inkludert nettstedet ditt, kjøp i butikken, fordelsprogrammer og så videre.

## <a name="sample-scenario"></a>Eksempelscenario

La oss ta en kaffekjede som eksempel. Den har en bred kundebase som kjøper kaffe og mat i butikker og bestiller produkter på nettet. Besøkende på nettet er ofte ikke godkjent når de ser gjennom produktene, slik at de er «ukjente brukere». Det er vanskelig for kaffekjeden å tilby tilpassede tilbud og opplevelser hvis brukerne er ukjente. Kunder kan på den annen side logge seg på kontoen og bli «kjente brukere» for firmaet ved å bli med i et lojalitetssystem, som igjen gir mer tilpassede opplevelser. Customer Insights kan hjelpe kaffekjeden å få innsikt i kjente og tidligere ukjente brukere.

Med Customer Insights kan firmaet kombinere kundeprofiler med aktivitetsdata fra ikke godkjente (ukjente) økter etter at en bruker har logget seg på og blitt kjent. Kaffekjeden kan sende data fra andre datakilder ved hjelp av innebygde koblinger til Customer Insights for å slå sammen identiteter for kunder fra ulike kanaler.

## <a name="prerequisites"></a>Forutsetning

- Nettdata samles inn og inneholder «besøkende-ID-er» for alle besøkende.
- Nettdata inneholder «godkjente bruker-ID-er» for påloggede besøkende. Disse ID-ene er koblet til fordelssystemet.
- Hendelsesdata av høy verdi, for eksempel «produktvisning» og «gå til kassen», defineres og tas med i kildedataene sammen med tidsstempelet for hendelsen og en hendelses-ID.

Tabellen nedenfor viser et forenklet eksempel på hvordan netthendelser av høy verdi kan registreres.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Produktvisning|
|2|07-23-2022 10:05:00|abc123|707|Fordelspålogging|
|3|07-23-2022 10:10:00|abc123|707|Utsjekking|
|4|07-23-2022 10:20:00|xyz789|--|Produktvisning|

## <a name="data-ingestion"></a>Datainntak

Data om kunder kan stamme fra nettstedet ditt som hendelsesdata, og de kan lagres i dine egne dataanalysetjenester eller de fra tredjeparter. Nettdataene inneholder kjente og ukjente brukere hvis nettstedet har en godkjenningsflyt som er integrert med en godkjenningstjeneste. Dette kan for eksempel være et eCommerce-system der brukerne må oppgi komplette detaljer for å fullføre en kjøpstransaksjon. Eller det kan være et fordelssystem der godkjenning kreves for å bekrefte en gyldig mottaker av rabatter.

Hendelsesdataene i eksemplet ovenfor inneholder distinkte profil-ID-er for kjente og ukjente brukere. I hendelse 1 og 4 er brukerne ukjente, mens i hendelse 2 og 3 registrerer brukeren med ID-en abc123 seg i et fordelsprogram.

:::image type="content" source="media/website-data-source.png" alt-text="Datakilder som omfatter Contoso-nettstedet.":::

Hvis du vil ha mer informasjon om de tilgjengelige alternativene for datainntak, kan du se [Oversikt over datakilder](data-sources.md).

## <a name="data-unification"></a>Datasamling

Når du får ukjente identiteter til å konvergere med kjente identiteter, blir det mulig å foreta tilpassing basert på brukeratferd, uavhengig av profiltilstanden deres (kjent eller ukjent). Tilpasset innhold for alle brukere hjelper kunder å få tilgang til de mest relevante produktene eller tjenestene de er interessert i for øyeblikket.

Siden det finnes noen kjente brukere i dataene, kan vi bruke Customer Insights til å kombinere disse dataene med brukerens profil. Hvis du vil ha mer informasjon om hvordan du samler kundeprofiler, kan du se [Oversikt over datasamling](data-unification.md).

1. Velg kildefeltene fra nettdataenheten. Bruk profildataene som er lagret i nettdataene, og velg feltene som representerer ID-er med demografiske data.

   :::image type="content" source="media/website-source-fields.png" alt-text="Kildefelter for nettdatakilden.":::

1. Legg til regler for å slå sammen duplikatoppføringer. Velg de mest utfylte dataene for nettdata.

1. Konfigurer samsvarsregler og -betingelser. Hendelsesdataene i nettprofiler samsvares i dette eksemplet mot ID-ene med profilene fra de andre datakildene som inneholder kundeinformasjon. Konfigurer regler for nøyaktig samsvar for ID-er som separate regler med hver av de andre profilenhetene som har en tilsvarende primærnøkkel eller ID som samsvarer. I eksemplet brukes profildata for netthendelse som den siste samsvarende enheten, slik at andre profildata kombineres først.
   1. Når du ikke merker av for **Inkluder alle oppføringer**, opprettes enhetlige profiler for kjente brukere, og de tilsvarende ukjent bruker-ID-ene deres inkluderes. Dette er nyttig i scenarioer der du er interessert i å vise tidligere atferdsaktiviteter for kjente brukere da de fortsatt var ukjente.
   1. Hvis du merker av for **Inkluder alle oppføringer**, opprettes separate profiloppføringer for ukjente brukere. Ukjente brukere får en unik kunde-ID. Når en kjent profil senere tilknyttes i profildataene for netthendelser, kan den nylig kjente brukerens reise vises og brukes til tilpassing også basert på tidligere ukjente atferdsdata.

:::image type="content" source="media/website-match-rule.png" alt-text="Samsvarsregel for datakildeenheten for nettsted.":::

## <a name="get-insights"></a>Få innsikt

Hvis kundeprofiler opprettes for ukjente og kjente brukere, kan netthendelsesdataene av høy verdi brukes som [aktiviteter](activities.md). Disse aktivitetene kan brukes til å skape mer innsikt. Kunder som for eksempel besøkte et nettsted for seks måneder siden (da de fortsatt var ukjente), eller kunder som ikke har en fordels-ID, fullførte aldri en betaling.

:::image type="content" source="media/website-known-unknown.png" alt-text="Skjermbilde av kundesiden med kjente og ukjente kunder.":::

[Suppler](enrichment-hub.md) dataene, bygg [mål](measures.md), og opprett [segmenter](segments.md) for videre aktivering.

Du kan for eksempel opprette segmenter for kjente brukere som så på noen produkter, men aldri fullførte betalingen.

Hvis du vil ha mer informasjon, kan du se [Segmentoversikt](segments.md).

## <a name="activate-insights"></a>Aktiver innsikt

Du kan eksportere dataene på flere måter og iverksette tiltak basert på den underliggende innsikten.

Hvis du vil ha mer informasjon, kan du se [Oversikt over eksporter](export-destinations.md).
