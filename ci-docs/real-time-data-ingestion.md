---
title: Datainntak i sanntid (forhåndsversjon)
description: Generell informasjon om sanntidsfunksjoner i Customer Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 39d68011df9e4341244af627bb71f4e3635256bb
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081729"
---
# <a name="real-time-data-ingestion-preview"></a>Datainntak i sanntid (forhåndsversjon)

Ved hjelp av den nær sanntidsfunksjonaliteten kan du se, i løpet av sekunder, de nyeste samhandlingene som kundene har gjort med dine produkter eller tjenester.

[Planlagte oppdateringer](system.md#schedule-tab) omfatter et stort antall oppføringer og flere komplekse operasjoner. Først hentes data inn fra datakilden. Deretter samles dataene og suppleres med tilleggsinformasjon. Hver utførelse av denne prosessen kan ta minutter til timer.

Sanntidsfunksjonaliteten gir data øyeblikkelig for forbruk, helt til den påfølgende planlagte oppdateringen henter disse dataene fra datakilden.

Oppdateringer i sanntid har en utløpstid da de ikke lenger overstyrer verdien fra datakilden:

- Profiloppdateringer vil beholdes i 4 timer
- Det beholdes aktiviteter i 30 dager

Disse verdiene er API-kallparametere som du kan endre. De skal sikre at kildedataene forblir sannhetskilden. Hvis du vil at sanntidsoppdateringer skal være inkludert lengre, må du legge dem til i en datakilde slik at de blir hentet under den neste planlagte oppdateringen.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Sanntidsoppdatering av de enhetlige kundeprofilfeltene

Oppdaterte profiler vises i kundekortvisningen, eller en hvilken som helst annen visualisering, i løpet av noen få sekunder.

Siden sanntidsoperasjoner foregår etter at datasamlingen har skjedd, gjelder de bare for de enhetlige kundeprofilene. Derfor oppdaterer ikke sanntidsprofilendringer mål, segmentmedlemskap eller suppleringer.

### <a name="limitations"></a>Begrensninger

- Kundeprofiler kan oppdateres, men ikke opprettes eller slettes.
- Det er ikke mulig å eksportere sanntidsoppdateringer til eksterne systemer, for eksempel Power BI.

## <a name="real-time-creation-of-activities"></a>Sanntidsopprettelse av aktiviteter

I sanntids-API-en kan du publisere en ny aktivitet fra kildesystemet (en individuell kildeoppføring) til en enhetlig kundeprofil. Den nye aktiviteten blir tilgjengelig som en ensartet aktivitet i den enhetlige kundeprofilens tidslinje i løpet av sekunder. Du kan se tidslinjen i kundekortvisningen eller en annen tidslinjeintegrering du har konfigurert.

> [!NOTE]
>
> - Aktivitetene er uforanderlige. De blir ikke endret etter at de er opprettet.
> - For øyeblikket oppdateres ikke segmenter og mål basert på den nye aktiviteten.
> - Aktiviteter som er lagt til bare via API-en i sanntid, er ikke en del av eksporter og vises ikke i PowerBI.

Du kan koble deg til sanntids-API-en på to måter:

- [indirekte](#connect-via-the-dynamics-365-customer-insights-connector) ved hjelp av [Dynamics 365 Customer Insights-koblingen](/connectors/customerinsights/)
- [direkte](#connect-directly-to-the-real-time-api), med kode

Følgende forutsetninger gjelder for begge:

- Et Customer Insights-miljø
- Enhetlige kundeprofiler
- Aktiviteter konfigurert og kjørt
- Bidragsyter eller administratortillatelser til å godkjenne kontoen

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Koble til via Dynamics 365 Customer Insights-koblingen

Sanntids-API-en kan inkludere data fra en dedikert Power Platform-kobling, [Dynamics 365 Customer Insights-koblingen](/connectors/customerinsights/), uten å måtte skrive og distribuere kode.    
Koblingen kan utføre samme sanntidshandlinger som API-en. Du trenger en gyldig lisens for Premium-koblinger. Hvis du vil ha mer informasjon, kan du se [Vanlige spørsmål om om lisensiering for Power Apps og Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps og/eller Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Hvis du vil ha informasjon om hvordan du oppretter flyter, kan du se i [Power Automate-dokumentasjonen](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Koble direkte til API i sanntid

Du kan bruke sanntidsfunksjonene ved å bygge din egen pipeline og direkte koble direkte til sanntids-API-en.    
Du kan legge inn en aktivitet i formatet til kildesystemet eller i UnifiedActivity-formatet. Få formatet ved å gjøre et API-kall til /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Detaljer om denne API-en, inkludert parametere og svar, finner du i **EntityData**-delen i [Referanse for API-er i Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Hvis du vil ha mer informasjon, kan du se [Arbeide med API-er i Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Forstå sanntidsbruk med telemetri

Få en oversikt over volumet av forespørsler til sanntids-API-en og informasjon om problemer som systemet kan støte på. Du får [tilgang til telemetrien i sanntid](system.md#api-usage-tab). 


[!INCLUDE [footer-include](includes/footer-banner.md)]
