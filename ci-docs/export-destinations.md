---
title: Eksportere data fra Customer Insights
description: Administrer eksporter for å dele data.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: 9c3b35f1514adcc697672f09cabf593f936e4a82
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646928"
---
# <a name="exports-preview-overview"></a>Oversikt over Eksporter (forhåndsversjon)

**Eksporter**-siden viser alle konfigurerte eksporter. Eksporter deler bestemte data med forskjellige programmer. De kan omfatte kundeprofiler, enheter, skjemaer og tilordningsdetaljer. Hver eksport krever en [tilkobling, konfigurert av en administrator, for å administrere godkjenning og tilgang](connections.md).

Gå til **Data** > **Eksporter** for å vise eksportsiden. Alle brukerroller kan vise konfigurerte eksporter. Bruk søkefeltet på kommandolinjen til å søke etter eksporter etter navn, tilkoblingsnavn eller tilkoblingstype.

## <a name="export-types"></a>Eksporttyper

Det finnes to hovedtyper av eksporter:  

- Med **Data-ut-eksporter** kan du eksportere alle typer enheter som er tilgjengelig i Customer Insights. Enhetene du velger for eksport, eksporteres med alle datafelt, metadata, skjemaer og tilordningsdetaljer. 
- **Segmenteksporter** lar deg eksportere segmentenheter fra Customer Insights. Segmenter representerer en liste over kundeprofiler. Når du konfigurerer eksporten, velger du de inkluderte datafeltene, avhengig av målsystemet du eksporterer data til. 

### <a name="export-segments"></a>Eksportere segmenter

**Eksporterer segmenter i miljøer for forretningskontoer (B-til-B) eller enkeltforbrukere (B-til-C)**  
De fleste eksportalternativ støtter begge typer miljøer. Eksport av segmenter til forskjellige målsystemer har spesifikke krav. Et segmentmedlem, kundeprofilen, inneholder generelt sett kontaktinformasjon. Selv om dette vanligvis er tilfellet for segmenter som er bygd på enkeltforbrukere (B-til-C), er det ikke nødvendigvis tilfellet for segmenter basert på forretningskontoer (B-til-B). 

**Segmenteksportmiljøer for forretningskontoer (B-til-B)**  
- Segmenter i konteksten for miljøer for forretningskontoer er bygd på *forretningsforbindels*-enheten. Hvis du vil eksportere forretningsforbindelsessegmenter som de er, må målsystemet støtte rene forretningsforbindelsessegmenter. Dette er tilfellet for [LinkedIn](export-linkedin-ads.md) når du velger **firma**-alternativet mens du definerer eksporten.
- Alle andre målsystemer krever felt fra kontaktenheten. For å sikre at segmenter for forretningsforbindelser kan hente data fra relaterte kontakter, må segmentdefinisjonen din projisere attributter for kontaktenheten. Lær mer om hvordan du [konfigurerer segmenter og prosjektattributter](segment-builder.md).

**Segmenteksporter i miljøer for enkeltforbrukere (B-til-C)**  
- Segmenter i konteksten for miljøer for individuelle kunder er bygd på enheten for *enhetlig kundeprofil*. Hvert segment som oppfyller kravene i målsystemet (for eksempel en e-postadresse), kan eksporteres.

**Begrensninger for segmenteksporter**  
- Tredjeparts målsystemer kan begrense antallet kundeprofiler du kan eksportere. 
- For enkeltkunder vises det faktiske antallet segmentmedlemmer når du velger et segment for eksport. Du får en advarsel hvis et segment er for stort. 
- For forretningskontoer vises antall forretningsforbindelser i et segment. Antall kontakter som kan projiseres, vises imidlertid ikke. I noen tilfeller kan dette føre til at det eksporterte segmentet faktisk inneholder flere kundeprofiler enn målsystemet godtar. Hvis du overskrider grensene for målsystemresultatene, hopper du over eksporten. 

## <a name="set-up-a-new-export"></a>Konfigurer en ny eksport  
Hvis du vil konfigurere eller redigere en eksport, må du ha tilkoblinger tilgjengelige for deg. Tilkoblinger avhenger av [brukerrollen din](permissions.md):
- **Administratorer** har tilgang til alle tilkoblinger. De kan også opprette nye tilkoblinger når de konfigurerer en eksport.
- **Bidragsytere** kan ha tilgang til bestemte tilkoblinger. De er avhengig av administratorer for å konfigurere og dele tilkoblinger. Eksporter-listen viser bidragsytere om de kan redigere eller bare vise en eksport, i kolonnen **Tillatelsene dine**. Hvis du vil ha mer informasjon, kan du gå til [Tillat bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Lesere** kan bare vise eksisterende eksporter – ikke opprette dem.

### <a name="define-a-new-export"></a>Definere en ny eksport

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport** for å opprette en ny eksport.

1. Velg hvilken tilkobling som skal brukes, i ruten **Konfigurer eksport**. [Tilkoblinger](connections.md) administreres av administratorer. 

1. Oppgi de nødvendige detaljene, og velg **Lagre** for å opprette eksporten.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definere en ny eksport basert på en eksisterende eksport

1. Gå til **Data** > **Eksporter**.

1. Velg eksporten du vil duplisere, i listen over eksporter.

1. Velg **Opprett duplikat** på kommandolinjen for å åpne ruten **Konfigurer eksport** med detaljene for den valgte eksporten.

1. Se gjennom og tilpass eksporten, og velg **Lagre** for å opprette en ny eksport.

### <a name="edit-an-export"></a>Rediger en eksport

1. Gå til **Data** > **Eksporter**.

1. Velg eksporten du vil redigere, i listen over eksporter.

1. Velg **Rediger** på kommandolinjen.

1. Endre verdiene du vil oppdatere, og velg **Lagre**.

## <a name="view-exports-and-export-details"></a>Vise eksporter og eksportdetaljer

Når du har opprettet eksportmål, vises de i **Data** > **Eksporter**. Alle brukere kan se hvilke data som deles, og den nyeste statusen.

1. Gå til **Data** > **Eksporter**.

1. Brukere uten redigeringstillatelser velger **Vis** i stedet for **Rediger** for å vise eksportdetaljene.

1. Sideruten viser konfigurasjonen av en eksport. Du kan ikke endre verdier uten redigeringstillatelser. Velg **Lukk** for å gå tilbake til eksportsiden.

## <a name="schedule-and-run-exports"></a>Planlegge og kjøre eksporter

Hver eksport du konfigurerer, har en oppdateringsplan. Under en oppdatering ser systemet etter nye eller oppdaterte data som skal tas med i en eksport. Eksporter kjører som standard som en del av hver [planlagte systemoppdatering](system.md#schedule-tab). Du kan tilpasse oppdateringsplanen eller deaktivere den for å kjøre eksporter manuelt.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Eksportplaner er avhengig av tilstanden til miljøet. Hvis det pågår oppdateringer for [avhengigheter](system.md#refresh-processes) når en planlagt eksport skal starte, fullføres oppdateringene først, og deretter kjøres eksporten. Du kan se når en eksport sist ble oppdatert, i kolonnen **Oppdatert**.

### <a name="schedule-exports"></a>Planlegge eksporter

Du kan definere egendefinerte oppdateringsplaner for individuelle eksporter eller flere eksporter samtidig. Den gjeldende definerte tidsplanen vises i **Tidsplan**-kolonnen i eksportlisten. Tillatelsen til å endre tidsplanen er den samme som for [redigering og definisjon av eksporter](export-destinations.md#set-up-a-new-export). 

1. Gå til **Data** > **Eksporter**.

1. Velg eksporten du vil planlegge.

1. Velg **Planlegg** på kommandolinjen.

1. Sett **Planlegg kjøring** til **På** i ruten **Planlegg eksport** for å kjøre eksporten automatisk. Sett den til **Av** for å oppdatere den manuelt.

1. Velg en verdi for **Gjentakelse** for automatisk oppdaterte eksporter, og angi detaljene for den. Den angitte tiden gjelder for alle forekomster av en gjentakelse. Det tidspunktet når en eksport skal begynne å oppdateres.

1. Bruk og aktiver endringene ved å velge **Lagre**.

Når du redigerer tidsplanen for flere eksporter, må du foreta et valg under **Behold eller overstyr tidsplaner**:
- **Behold individuelle tidsplaner**: Behold den tidligere definerte tidsplanen for de valgte eksportene, og bare deaktiver eller aktiver dem.
- **Definer ny tidsplan for alle valgte eksporter**: Overstyr de eksisterende tidsplanene for de valgte eksportene.

### <a name="run-exports-on-demand"></a>Kjør eksporter ved behov

Hvis du vil eksportere data uten å vente på en planlagt oppdatering, går du til **Data** > **Eksporter**.

- Hvis du vil kjøre alle eksporter, velger du **Kjør alle** på kommandolinjen. Denne handlingen kjører bare eksporter som har en aktiv tidsplan.
- Hvis du vil kjøre én eksport, merker du den i listen og velger **Kjør** på kommandolinjen. Det er slik du kjører eksporter uten en aktiv tidsplan. 

## <a name="remove-an-export"></a>Fjerne en eksport

1. Gå til **Data** > **Eksporter**.

1. Velg eksporten du vil fjerne.

1. Velg **Fjern** på kommandolinjen.

1. Bekreft fjerningen ved å velge **Fjern** i bekreftelsesdialogboksen.


[!INCLUDE [footer-include](includes/footer-banner.md)]