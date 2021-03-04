---
title: Integrere nettdata fra engasjementsinnsikt med målgruppeinnsikt
description: Hent nettinformasjon om kunder fra engasjementsinnsikt til målgruppeinnsikt.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mukeshpo
manager: shellyha
ms.openlocfilehash: ba1cf6c7e85b8fe90baf34018f1309095573adf1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267688"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrere nettdata fra engasjementsinnsikt med målgruppeinnsikt

Kunder gjør ofte sine daglige transaksjoner på Internett ved hjelp av nettsteder. Engasjementsinnsiktsfunksjonen i Dynamics 365 Customer Insights er en nyttig løsning for å integrere nettdata som en kilde. I tillegg til transaksjonsdata, demografiske data eller atferdsdata kan vi se aktiviteter på Internett i enhetlige kundeprofiler. Vi kan bruke denne profilen til å få mer innsikt, for eksempel segmenter, tiltak eller prediksjoner for målgruppeaktivering.

Denne artikkelen beskriver fremgangsmåten for å hente kundenes nettaktivitetsdata fra engasjementsinnsikt i det eksisterende målgruppeinnsiktsmiljøet.

I dette eksemplet antar vi et miljø som inneholder enhetlige kundeprofiler. Profilene var forenet med kilder fra undersøkelser, detaljsalg og et billettsystem. Den viser også de relaterte aktivitetene til kundene. 

Vi vil nå vite om en kunde besøker nettegenskapene og forstå aktivitetene deres. Aktiviteter omfatter for eksempel besøkte nettsteder eller viste produktsider fra en kobling mottatt via e-post.

## <a name="prerequisites"></a>Forutsetninger

Noen få forhåndskrav må oppfylles for å kunne integrere data fra engasjementsinnsikt: 

- Integrer SDK-et for engasjementsinnsikt med nettstedet ditt. Hvis du vil ha mer informasjon, kan du se [Kom i gang med nett-SDK-et](../engagement-insights/instrument-website.md).
- Eksport av netthendelser fra engasjementsinnsikt krever tilgang til en ADLS Gen 2-lagringskonto som blir brukt til å samle inn netthendelsesdataene til målgruppeinnsikt. Hvis du vil ha mer informasjon, kan du se [Eksporter hendelser](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfigurer begrensede hendelser i engasjementsinnsikt

Når en administrator instrumenterte et nettsted med SDK-et for engasjementsinnsikt, samles *basishendelser* når en bruker viser en nettside eller klikker et sted. Basishendelser inneholder en rekke detaljer. Avhengig av bruksaken trenger du bare et delsett av dataene i en basishendelse. Engasjementsinnsikt gjør det enkelt å opprette *begrensede hendelser* som bare inneholder egenskapene for en basishendelse du velger.     

Hvis du vil ha mer informasjon, kan du se [Opprett og endre begrensede hendelser](../engagement-insights/refined-events.md).

Vurderinger ved oppretting av begrensede hendelser: 

- Angi et beskrivende navn for den begrensede hendelsen. Den brukes som et aktivitetsnavn i målgruppeinnsikt.
- Velg minst følgende egenskaper for å opprette en aktivitet i målgruppeinnsikt: 
    - Signal.Action.Name – angir aktivitetsdetaljene
    - Signal.User.Id – brukes til å tilordne med kunde-ID-en
    - Signal.View.Uri – brukes som en nettadresse som grunnlag for segmenter eller tiltak
    - Signal.Export.Id – brukes som primærnøkkel for hendelser <!-- system generated, do we need to list?-->
    - Signal.Timestamp – for å bestemme datoen og klokkeslettet for aktiviteten

Velg filtrene for å fokusere på hendelser og sider som er viktige for ditt bruksområde. I dette eksemplet bruker vi handlingsnavnet E-postkampanje.

## <a name="export-the-refined-web-events"></a>Eksportere de begrensede netthendelsene 

Når du har definert den begrensede hendelsen, må du konfigurere eksporten av hendelsesdataene til en Azure Data Lake Storage, som kan angis som en datakilde for inntak i målgruppeinnsikt. Eksporter skjer hele tiden etter hvert som hendelsene strømmer fra nettegenskapen.

Hvis du vil ha mer informasjon, kan du se [Eksporter hendelser](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Legg inn hendelsesdata til målgruppeinnsikt

Nå som du har definert den begrensede hendelsen og konfigurert eksporten, går vi videre til å legge inn dataene til målgruppeinnsikt. Du må opprette en ny datakilde basert på en Common Data Model-mappe. Angi detaljene for lagringskontoen du eksporterer hendelsene til. I filen *default.cdm.json* velger du den begrensede hendelsen som skal inntas, og oppretter enheten i målgruppeinnsikt.

Hvis du vil ha mer informasjon, kan du se [Koble til en Common Data Model-mappe ved hjelp av en Azure Data Lake-konto](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Relatere begrensede hendelsesdata som en aktivitet for en kundeprofil

Når du har fullført inntaket av enheten, kan du konfigurere aktiviteten for kundeprofilen.

Hvis du vil ha mer informasjon, kan du se [Kundeaktiviteter](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Aktiviteter-siden med den utvidede Rediger aktivitet-ruten og utfylte felter.":::

Konfigurer den nye aktiviteten med følgende tilordning: 

- **Hovednøkkel:** Signal.Export.Id, en unik ID som er tilgjengelig for hver hendelsesoppføring i engasjementsinnsikt. Denne egenskapen genereres automatisk.

- **Tidsstempel:** Signal.Timestamp i hendelsesegenskapen.

- **Hendelse:** Signal.Name, hendelsesnavnet du vil spore.

- **Nettadresse:** Signal.View.Uri som refererer til URI-en til siden som opprettet hendelsen.

- **Detaljer:** Signal.Action.Name som representerer informasjonen som skal knyttes til hendelsen. Den valgte egenskapen i dette tilfellet angir at hendelsen gjelder for e-postkampanje.

- **Aktivitetstype:** I dette eksemplet velger vi den eksterne aktivitetstypen WebLog. Dette valget er et nyttig filteralternativ for å kjøre prediksjonsmodeller eller opprette segmenter basert på denne aktivitetstypen.

- **Konfigurer relasjon:** Denne viktige innstillingen binder aktiviteten til eksisterende kundeprofiler. **Signal.User.Id** er identifikatoren som er konfigurert i SDK-et som skal samles inn, og som er relatert til bruker-ID-en i andre datakilder som er konfigurert i målgruppeinnsikt. I dette eksemplet konfigurerer vi relasjonen mellom Signal.User.Id og RetailCustomers:CustomerRetailId, som er primærnøkkelen som ble definert i tilordningstrinnet i dataforklaringsprosessen.


Når du har behandlet aktivitetene, kan du se gjennom kundeoppføringer og åpne et kundekort for å se aktiviteter fra engasjementsinnsikt på tidslinjen. 

> [!TIP]
> Hvis du vil finne en kunde-ID som har en engasjementsinnsiktsaktivitet, går du til **Enheter** og forhåndsviser dataene for UnifiedActivity-enheten. ActivityTypeDisplay = WebLog inneholder engasjementsinnsiktsaktiviteten som er konfigurert i eksemplet ovenfor. Kopier kunde-ID-en for en av disse oppføringene og for ID-en på **Kunder**-siden.

## <a name="next-steps"></a>Neste trinn

Du kan nå opprette [segmenter](segments.md), [mål](measures.md) og [prediksjoner](predictions.md) for å skape en meningsfylt forbindelse med kundene.


[!INCLUDE[footer-include](../includes/footer-banner.md)]