---
title: Behandle ukjente profiler med Customer Insights
description: Arbeid med ukjente kundeprofiler som opprettes og behandles i Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776833"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Behandle ukjente profiler med Customer Insights

Internett-brukere er ofte uidentifiserte eller anonyme på Internett. Selv de mest lojale kundene kan se ut som «ukjente» hvis de ikke er pålogget på tvers ulike enheter. For mange merker er kjente eller godkjente brukere i mindretall, til tross for økende kundeforventninger i form av tilpassing. Siden fremtiden til informasjonskapsler fra tredjeparter er usikker, er det avgjørende å administrere brukerpreferanser basert på førstepartsdata i stedet for å oppnå tilpassede opplevelser.

Minneverdig tilpassing avhenger av hvor godt du kjenner kunden, og Customer Insights hjelper deg å gjøre dette ved å spore alle kundene dine.  Du trenger ikke begrense eller stoppe bruken av data som samles inn i begynnelsen av kundereisen. Med Customer Insights kan du hente dine egne data for å opprette en kundeprofil for ukjente brukere. Du kan deretter bruke denne profilen til flere handlinger, til tross for manglende kontaktinformasjon. Importer førstepartsdata fra kilder som nett-, mobil- eller CRM-systemer til Customer Insights for å supplere kundeprofilene kontinuerlig. Etter hvert som du forener flere samhandlinger, [kan du gjøre den *ukjente* kunden om til en *kjent* kunde](unknown-to-known.md).

## <a name="sample-scenario"></a>Eksempelscenario

Anta at en bruker bruker en mobilenhet til å bla gjennom nettstedet ditt for e-handel. Nettstedet tilordner den besøkende "mobile_guest123" som en unik identifikator, og du begynner å samle inn atferdsaktiviteter basert på aktiviteten på nettet. Eksempel: hvilke sider de besøkte, hvor mye tid de brukte på disse sidene, eller hvilke koblinger de klikket på. Du kjenner ikke til navnet eller e-postadressen, men disse dataene kan bidra til at varemerker får meningsfull innsikt om denne bestemte brukeren. Du kan igjen bruke denne innsikten neste gang brukeren besøker nettstedet. Spør Customer Insights om "mobile_guest123" for å hente brukerens segmentliste, for eksempel "organisk", "forhåndsordrekunder på mobil", "verdifulle kunder" og så videre, eller hent profilen for å opprette tilpassede nettopplevelser. Du kan også eksportere dataene til et aktiveringssystem for å gjøre det samme.

## <a name="prerequisites"></a>Forutsetning

- Registrer førstepartsdata i Customer Insights
- Hver enhet har en unik ID som er angitt som en primærnøkkel
- Hver enhet med en primærnøkkel for tilpassing er enhetlig
- Innholdsbehandlingssystemet for nettstedet kan bruke API-er (for tilpassing på nettet basert på direkte kommunikasjon med Customer Insights)

Tabellen nedenfor viser et forenklet eksempel på hvordan netthendelser av høy verdi kan registreres.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Produktvisning|
|2|09-18-2022 10:05:00|abc123|CookieID1|Produktvisning|
|3|09-18-2022 10:10:00|abc123|CookieID1|Legg til i handlekurv|
|4|09-21-2022 09:05:00|abc123|CookieID1|Produktvisning|

## <a name="data-ingestion"></a>Datainntak

Hvis du vil ha mer informasjon om de tilgjengelige alternativene for datainntak, kan du se [Oversikt over datakilder](data-sources.md).

## <a name="data-unification"></a>Datasamling

Hvis du vil ha mer informasjon om hvordan du samler kundeprofiler, kan du se [Oversikt over datasamling](data-unification.md).

## <a name="get-insights"></a>Få innsikt

[Suppler](enrichment-hub.md) dataene, bygg [mål](measures.md), og opprett [segmenter](segments.md) for videre aktivering.

Du kan for eksempel opprette segmenter med ukjente brukere som har bladd gjennom de samme produktsidene, men aldri fullført betalingen.

## <a name="activation"></a>Aktivering

Når du har dataene dine i Customer Insights og er klat til å bruke innsikten, kan du bruke Customer Insights til tilpassing:

1. Bruk [OData-API-en](apis.md) til å hente et segmentmedlemskap eller en kundeprofil. Hvis du vil ha flere eksempler, kan du se [OData-spørringseksempler for API-er for Customer Insights](odata-examples.md).

1. [Eksporter](export-destinations.md) dataene til aktiveringssystemene.

Eksempel: En ukjent bruker besøker et nettsted flere ganger og går til produktsider for ulike modeller av sko i ekte skinn. Med disse dataene tilgjengelige i Customer Insights kan du inkludere den ukjente brukeren i segmentet av personer som er interessert i sko i ekte skinn. Bruk dette segmentet til å informere nettstedet om å bygge tilpassing for returnerende gjester. Ved neste besøk gjenkjenner nettstedet den ukjente brukeren og kan tilby vedkommende en 10 % rabattkupong på sko i ekte skinn.

[!INCLUDE [footer-include](includes/footer-banner.md)]
