---
title: Oversikt over Eksporter (forhåndsversjon)
description: Administrer eksporter for å dele data.
ms.date: 08/12/2022
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
ms.openlocfilehash: c580b6c01e1b4ac6b095733193d86ebd0b4005f2
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304071"
---
# <a name="exports-preview-overview"></a>Oversikt over Eksporter (forhåndsversjon)

 Eksporter lar deg dele bestemte data med forskjellige programmer. De kan omfatte kundeprofiler, enheter, skjemaer og tilordningsdetaljer. Hver eksport krever en [tilkobling, konfigurert av en administrator, for å administrere godkjenning og tilgang](connections.md). **Eksporter**-siden viser alle konfigurerte eksporter.

## <a name="export-types"></a>Eksporttyper

Det finnes to hovedtyper av eksporter:  

- Med **Data-ut-eksporter** kan du eksportere alle typer enheter som er tilgjengelig i Customer Insights. Enhetene du velger for eksport, eksporteres med alle datafelt, metadata, skjemaer og tilordningsdetaljer.
- **Segmenteksporter** lar deg eksportere segmentenheter fra Customer Insights. Segmenter representerer en liste over kundeprofiler for enkeltpersoner (B2C). For virksomheter (B2B) [kan segmenter representere en liste over forretningsforbindelser eller kontakter](segment-builder.md#create-a-new-segment-with-segment-builder). Når du konfigurerer eksporten, velger du de inkluderte datafeltene, avhengig av målsystemet du eksporterer data til.

### <a name="export-segments"></a>Eksportere segmenter

**Eksporterer segmenter i miljøer for forretningskontoer (B-til-B) eller enkeltforbrukere (B-til-C)**  
De fleste eksportalternativer støtter begge typer miljøer. Eksport av segmenter til forskjellige målsystemer har spesifikke krav. 

**Segmenteksporter i miljøer for enkeltforbrukere (B-til-C)**  
- Segmenter i konteksten for miljøer for individuelle kunder er bygd på enheten for *enhetlig kundeprofil*. Hvert segment som oppfyller kravene i målsystemet (for eksempel en e-postadresse), kan eksporteres.

**Segmenteksporter i miljøer for forretningskontoer (B2B)**  
- Segmenter i konteksten for miljøer for forretningskontoer er bygd på *forretningsforbindelse*-enheten eller *kontakt*-enheten. Hvis du vil eksportere forretningsforbindelsessegmenter som de er, må målsystemet støtte rene forretningsforbindelsessegmenter. Dette er tilfellet for [LinkedIn](export-linkedin-ads.md) når du velger **firma**-alternativet mens du definerer eksporten.
- Alle andre målsystemer krever felt fra kontaktenheten.
- Med to segmenttyper (kontakter og forretningsforbindelser) identifiserer Customer Insights automatisk hvilken type segmenter som kvalifiserer for eksport basert på målsystemet. Når det for eksempel gjelder et kontaktfokusert målsystem som Mailchimp, kan du bare eksportere kontaktsegmenter i Customer Insights.

**Begrensninger for segmenteksporter**  
- Tredjeparts målsystemer kan begrense antallet kundeprofiler du kan eksportere. 
- For enkeltkunder vises det faktiske antallet segmentmedlemmer når du velger et segment for eksport. Du får en advarsel hvis et segment er for stort. 
- For forretningskontoer ser du antall forretningsforbindelser eller kontakter avhengig av segmentet. Du får en advarsel hvis segmentet er for stort. Hvis du overskrider grensene for målsystemresultatene, hopper du over eksporten.

## <a name="set-up-a-new-export"></a>Konfigurer en ny eksport

Hvis du vil konfigurere eller redigere en eksport, må du ha de riktige tilkoblingene tilgjengelige for deg. Tilkoblinger avhenger av [brukerrollen din](permissions.md):
- **Administratorer** har tilgang til alle tilkoblinger. De kan også opprette nye tilkoblinger når de konfigurerer en eksport.
- **Bidragsytere** kan ha tilgang til bestemte tilkoblinger. De er avhengig av administratorer for å konfigurere og dele tilkoblinger. Eksporter-listen viser bidragsytere om de kan redigere eller bare vise en eksport, i kolonnen **Tillatelsene dine**. Hvis du vil ha mer informasjon, kan du gå til [Tillat bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Lesere** kan bare vise eksisterende eksporter – ikke opprette dem.

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport** for å opprette en ny eksport.

1. Velg hvilken [tilkobling](connections.md) som skal brukes, i ruten **Konfigurer eksport**.

1. Oppgi de nødvendige detaljene, og velg **Lagre** for å opprette eksporten. Når det gjelder nødvendige detaljer, ser du gjennom Customer Insights-dokumentasjonen for den bestemte eksporten.

## <a name="manage-existing-exports"></a>Administrer eksisterende eksporter

Gå til **Data** > **Eksporter** for å vise eksportene samt tilkoblingsnavnet, tilkoblingstypen og statusen deres. Alle brukerroller kan vise konfigurerte eksporter. Du kan sortere listen over eksporter etter en hvilken som helst kolonne, eller bruke søkefeltet til å finne eksporten du vil administrere.

Velg en eksport for å vise tilgjengelige handlinger.

:::image type="content" source="media/exports_showmore.png" alt-text="Eksporter-siden.":::

- **Vis** eller **Rediger** eksporten. Brukere uten redigeringstillatelser velger **Vis** i stedet for **Rediger** for å vise eksportdetaljene.
- **Kjør** eksporten for å eksportere de nyeste dataene.
- **Opprett duplikat** av en eksport.
- **[Planlegg](#schedule-and-run-exports)** eksporten.
- **Fjern tilkobling** for å fjerne tilkoblingen for denne eksporten. Fjern fjerner ikke tilkoblingen, men deaktiverer eksporten. Kolonnen **Tilkobling brukt** viser Ingen tilkobling.
- **Fjern** eksporten.

## <a name="schedule-and-run-exports"></a>Planlegge og kjøre eksporter

Hver eksport du konfigurerer, har en oppdateringsplan. Under en oppdatering ser systemet etter nye eller oppdaterte data som skal tas med i en eksport. Eksporter kjører som standard som en del av hver [planlagte systemoppdatering](schedule-refresh.md). Du kan tilpasse oppdateringsplanen eller deaktivere den for å kjøre eksporter manuelt.

Eksportplaner er avhengig av tilstanden til miljøet. Hvis det pågår oppdateringer for [avhengigheter](system.md#refresh-processes) når en planlagt eksport skal starte, fullføres oppdateringene først, og deretter kjøres eksporten. Kolonnen **Oppdatert** viser når en eksport sist ble oppdatert.

### <a name="schedule-exports"></a>Planlegge eksporter

Definer egendefinerte oppdateringsplaner for individuelle eksporter eller flere eksporter samtidig. Den gjeldende definerte tidsplanen vises i **Tidsplan**-kolonnen i eksportlisten. Tillatelsen til å endre tidsplanen er den samme som [redigering og definisjon av eksporter](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg eksporten du vil planlegge.

1. Velg **Planlegg**.

1. Sett **Planlegg kjøring** til **På** i ruten **Planlegg eksport** for å kjøre eksporten automatisk. Sett den til **Av** for å oppdatere den manuelt.

1. Velg en verdi for **Gjentakelse** for automatisk oppdaterte eksporter, og angi detaljene for den. Den angitte tiden gjelder for alle forekomster av en gjentakelse. Det tidspunktet når en eksport skal begynne å oppdateres.

1. Velg **Lagre**.

Når du redigerer tidsplanen for flere eksporter, foretar du et valg under **Behold eller overstyr tidsplaner**:

- **Behold individuelle tidsplaner**: Behold den tidligere definerte tidsplanen for de valgte eksportene, og bare deaktiver eller aktiver dem.
- **Definer ny tidsplan for alle valgte eksporter**: Overstyr de eksisterende tidsplanene for de valgte eksportene.

### <a name="run-exports-on-demand"></a>Kjør eksporter ved behov

Hvis du vil eksportere data uten å vente på en planlagt oppdatering, går du til **Data** > **Eksporter**.

- Hvis du vil kjøre alle eksporter, velger du **Kjør alle** på kommandolinjen. Bare eksporter som har en aktiv tidsplan, kjører. Hvis du vil kjøre en eksport som ikke er aktiv, kjører du én eksport.
- Hvis du vil kjøre én eksport, merker du den i listen og velger **Kjør** på kommandolinjen.

## <a name="troubleshooting"></a>Feilsøking

### <a name="segment-not-eligible-for-export"></a>Segmentet kvalifiserer ikke for eksport

**Problem** I et miljø med forretningskontoer mislykkes eksporten med feilmeldingen: «Følgende segment er ikke kvalifisert for dette eksportmålet: '{navn på segment}'. Velg bare segmenter av typen ContactProfile, og prøv på nytt.»

**Løsning** Customer Insights-miljøer for forretningskontoer ble oppdatert for å støtte kontaktsegmenter i tillegg til forretningsforbindelsessegmenter. Derfor fungerer eksporter som bare trenger kontaktinformasjon, med segmenter basert på kontakter.

1. [Opprett et segment basert på kontakter](segment-builder.md) som samsvarer med det tidligere brukte segmentet.

1. Når dette kontaktsegmentet er kjørt, redigerer du den respektive eksporten og velger det nye segmentet.

1. Velg **Lagre** for å lagre konfigurasjonen eller **Lagre og kjør** for å teste denne eksporten med en gang.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
