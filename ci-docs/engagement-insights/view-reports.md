---
title: Vis datarapporter
description: Bruk de tilgjengelige rapportene til å se aktivitet i sanntid på nettstedet ditt.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 03b0b4bab0d5d9c2ae641c85aac8174ec1668d45
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229752"
---
# <a name="view-reports"></a>Vis rapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En rapport er en samling datavisualiseringer som bruker dataene som samles inn via SDK, som hjelper deg med å måle og forstå brukeratferd. Dynamics 365 Customer Insights-engasjementsinnsikt inkluderer standardrapporter for web- og mobilprosjekter.  

## <a name="web-reports"></a>Webrapporter

Du kan få tilgang til webrapporter under **Oppdag** i den venstre navigasjonsruten.

:::image type="content" source="media/report-menu.png" alt-text="Navigasjon som viser listen over tilgjengelige rapporter.":::

### <a name="real-time-usage-report"></a>Bruksrapport i sanntid

Rapporten om **sanntidsbruk** gir en oversikt over gjeldende aktivitet på nettstedet ditt som automatisk oppdateres hvert minutt. Bruk sanntidsbruk til å overvåke virkningen av markedsføringskampanjer, pressehendelser og andre scenarioer for trafikk på området.

### <a name="key-metrics-reports"></a>Nøkkeltallrapporter

- **Sidevisninger** viser sidevisningene for enkeltsider sammen med antall samlede sidevisninger i den valgte tidsrammen.

- **Besøk** viser informasjon om antall besøk og besøksvarigheten.

- **Besøkende** informerer om nye og returnerende unike besøkende på webområdet.

### <a name="content-reports"></a>Innholdsrapporter

- **Koblinger** viser informasjon om antall og type klikk.

- **Forlat sider** viser koblingene som besøkende klikket for å avslutte området.

### <a name="traffic-sources-reports"></a>Rapporter om trafikkilder

- **Henvisere** viser domenene og URL-adressene som henviste besøkende til området ditt.

- **Sporingskoder** inneholder detaljer om sporingskodene i koblingene som førte til at besøkende kom til webområdet ditt.

### <a name="visitor-profiles-reports"></a>Rapporter om besøksprofiler

- **Enheter** viser de fysiske enhetene som ble brukt for å få tilgang til området ditt.

- **Operativsystem og nettlesere** gir deg innsikt i operativsystemene og nettleserne som kjørte da du fikk tilgang til området.

- **Steder** viser informasjon om besøkende etter land, område og by.

- **Språk** viser sidevisninger etter den besøkendes foretrukne språk.

## <a name="mobile-reports"></a>Mobilrapporter

Mobilrapporter grupperes i sanntidsbruk, app og brukerkategorier. Du kan få tilgang til mobilrapporter under **Oppdag** i den venstre navigasjonsruten.   

:::image type="content" source="media/mobile-reports.png" alt-text="Brukergrensesnitt for engasjementsinnsikt som viser bruksrapport i sanntid som gjengir data i diagrammer og lister.":::   

### <a name="real-time-usage"></a>Bruk i sanntid

**Bruk i sanntid** gir en oversikt over gjeldende aktivitet i mobilappen som oppdateres automatisk hvert minutt. Bruk sanntidsbruk til å overvåke antall brukere og økter som er aktive i appen, og topp skjermbildevisninger.

### <a name="app-reports"></a>Apprapporter

- **Skjermvisninger** viser skjermvisninger for enkeltskjermer i en app og totalt antall skjermvisninger over en valgt tidsramme. Du kan vise skjermvisninger etter skjermnavn eller skjermtittel.

- **Økter** viser informasjon om antall økter og øktvarigheten.

- **Returfrekvens** grupperer øktantall etter antall dager siden forrige økt.

- **Brukere** viser nye og returnerende brukere i mobilappen.

- **Hendelser** viser alle hendelsene som samles inn fra appen din, i tillegg til det totale antallet for hver hendelse.

### <a name="user-reports"></a>Brukerrapporter

- **Appversjoner** viser versjonene av mobilappen som brukes av brukerbasen din.

- **Enheter og operativsystemversjoner** gir innsikt i hvilke enheter og operativsystemer som kjører mobilappen din.

- **Steder** viser informasjon om appbrukere etter land, område og by.

## <a name="filter-by-time-or-date-range"></a>Filtrere etter klokkeslett eller datointervall

Du kan velge datotidsramme eller datointervall i en web- eller mobilrapport for å fokusere på en verdi eller tidsperiode. 

- For å velge en tidsramme velger du en verdi fra rullegardinlisten for rapporten i øvre høyre hjørne av rapportvisningen. Du kan også velge **Fast datointervall**. 

  :::image type="content" source="media/filter-by-time.png" alt-text="Filtrere etter klokkeslett eller datointervall.":::   

- For de fleste rapporter velger du en verdi i et diagram eller en liste for å filtrere rapporten.

> [!NOTE]
> Tidsintervallvalget er deaktivert for en rapport om sanntidsbruk. Tidsintervallet for en rapport om sanntidsbruk er «nå».


[!INCLUDE[footer-include](../includes/footer-banner.md)]
