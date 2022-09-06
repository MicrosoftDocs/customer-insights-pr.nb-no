---
title: DSR-forespørsler (Data Subject Rights) under GDPR | Microsoft Docs
description: Svare på dataemneforespørsler for Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387123"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>DSR-forespørsler (Data Subject Rights) under GDPR

EUs personvernforordning (GDPR) har vært gjeldende siden 25. mai 2018. Den gir personer betydelige rettigheter når det gjelder opplysningene deres. GDPR handler om å beskytte og ivareta personvernrettighetene til enkeltpersoner. Les mer om Microsofts engasjement for sikkerhet og overholdelse i [Microsoft Klareringssenter](https://www.microsoft.com/trust-center).

Vi går inn for å hjelpe kundene våre med å oppfylle GDPR-kravene. Den inkluderer retten til å slette eller eksportere data som inneholder personlige opplysninger, for eksempel bruker-ID-er, telefonnumre og e-postadresser. Administratorer kan implementere brukerforespørsler om å slette eller eksportere personlige opplysninger.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Svare på forespørsler om å slette GPDR-dataemner for Customer Insights

"Retten til å fjerne" personlige data fra en organisasjons kundedata er en nøkkelbeskyttelse i EUs personvernforordning (GDPR). Fjerning av personlige data inkluderer fjerning av alle personlige data og systemgenererte logger, unntatt revisjonslogginformasjon.

### <a name="manage-data-subject-delete-requests"></a>Behandle slettingsforespørsler for dataemner

Customer Insights tilbyr følgende produkterfaringer for å slette personlige data for en bestemt kunde eller Customer Insights-bruker:

- **Behandle sletteforespørsler for kundedata**: Kundedata i Customer Insights er innhentet fra opprinnelige datakilder som ikke er i Customer Insights. Utfør GDPR-sletteforespørsler i den opprinnelige datakilden først.
- **Behandle sletteforespørsler for Customer Insights-brukerdata**: Data for brukere opprettes av Customer Insights. Utføre alle GDPR-sletteforespørsler i Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Administrer forespørsler for å slette kundedata

Som en Customer Insights-administrator fjerner du Customer Insights-kundedata som ble slettet i datakilden. Kontroller at alle GDPR-sletteforespørsler ble utført i den opprinnelige datakilden.

1. Logg på Dynamics 365 Customer Insights.

1. Gå til **Data** > **Datakilder**.

1. For hver datakilde i listen som inneholder slettede kundedata:
   1. Velg datakilden, og velg deretter **Oppdater**.
   1. Kontroller statusen for datakilden under **Status**. Et merke betyr at oppdateringen var vellykket. En varseltrekant betyr at noe gikk galt. Hvis det vises en varseltrekant, kontakter du D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Behandle GDPR-sletteforespørsler for kundedata.":::

1. Etter en vellykket datakildeoppdatering kjører du nedstrømsoppdateringene også. Særlig hvis du ikke har en regelmessig, full oppdatering av Customer Insights planlagt.

   > [!IMPORTANT]
   > Statiske segmenter tas ikke med i en full oppdatering eller kjørende nedstrømsoppdateringer etter en sletteforespørsel. Du kan sikre at kundedata også fjernes fra statiske segmenter, ved å opprette de statiske segmentene på nytt med de oppdaterte kildedataene.

#### <a name="manage-delete-requests-for-user-data"></a>Behandle sletteforespørsler for brukerdata

Som Customer Insights-administrator sletter du Customer Insights-brukerdata.

1. Logg på Dynamics 365 Customer Insights.

1. Gå til **Administrator** > **Sikkerhet** > og velg fanen **Brukere**.

1. Merk av for brukerne du vil slette.

1. Velg **Fjern**.

1. Bekreft slettingen.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Svare på forespørsler om eksport av GDPR-dataemne

Med rettigheten for dataflyttbarhet kan dataemner be om en kopi av personlige data i et elektronisk format (et "strukturert, vanlig brukt, maskinlesbart og kompatibelt format") som kan overføres til en annen datakontroller.

### <a name="manage-export-and-view-requests"></a>Behandle eksport- og visningsforespørsler

Administrer forespørsler for å eksportere kunde- eller brukerdata.

#### <a name="export-customer-data-tenant-admin"></a>Eksportere kundedata (leieradministrasjon)

Som leieradministrator eksporterer du kundedata.

1. Send en e-post til D365CI@microsoft.com for å angi kundens e-postadresse i forespørselen. Customer Insights-teamet sender en e-post til den registrerte e-postadressen til leieradministratoren og ber om bekreftelse på å eksportere data.
2. Godta bekreftelsen om å eksportere dataene for den forespurte kunden.
3. Motta de eksporterte dataene via e-postadressen for leieradministratoren.

#### <a name="export-user-data-tenant-admin"></a>Eksportere brukerdata (leieradministrasjon)

Som leieradministrator eksporterer du brukerdata.

1. Send en e-post til D365CI@microsoft.com for å angi brukerens e-postadresse i forespørselen. Customer Insights-teamet sender en e-post til den registrerte e-postadressen til leieradministratoren og ber om bekreftelse på å eksportere data.
1. Godta bekreftelsen om å eksportere dataene for den forespurte brukeren.
1. Motta de eksporterte dataene via e-postadressen for leieradministratoren.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Håndtering av datasletting i Dynamics 365 Customer Insights

Data slettes (datapartisjoner og øyeblikksbilder) hvis datapartisjonene og øyeblikksbildene av data er inaktive i mer enn 30 dager, det vil si at de er erstattet av en ny datapartisjon og et øyeblikksbilde gjennom en oppdatering av datakilder.

Ikke alle data og øyeblikksbilder blir slettet. Den nyeste datapartisjonen og øyeblikksbildet av data er aktive fordi de brukes i Customer Insights. Når det gjelder de nyeste dataene, spiller det ingen rolle om datakildene ikke ble oppdatert i løpet av de siste 30 dagene.

[!INCLUDE [footer-include](includes/footer-banner.md)]
