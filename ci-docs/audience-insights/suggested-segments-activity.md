---
title: Foreslåtte segmenter basert på aktivitet.
description: La maskinlæring hjelpe deg med å finne nye og interessante segmenter basert på kundeaktivitet.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 9c10a32b770ea110a1166f20f72116a3a12cb92e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354475"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Foreslåtte segmenter basert på aktivitsdata (forhåndsversjon)

Oppdag interessante segmenter av kundene basert på kundeaktivitetsdata som er hentet inn i Customer Insights. Eksempler på aktivitetsdata er transaksjoner, samtalevarighet, kjøp eller returer. For å foreslå segmenter analyseres aktivitetsdata for nylighet, hyppighet og pengeverdi (eller varighet). Du kan også generere [foreslåtte segmenter for å forbedre et mål, eller bedre forstå hva som har innvirkning på et attributt](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Fanen Foreslåtte segmenter som viser segmentforslag for aktivitetsbaserte og attributtbaserte segmenter.":::

## <a name="categorize-customers-by-activity"></a>Kategoriser kunder etter aktivitet

Med [aktivitetsdata](activities.md) tilgjengelige i Customer Insights kan vi generere forslag som representerer kundegrupper:

- mest aktive kunder 
- kunder som har gjort flest kjøp 
- kunder som genererte mest omsetning 
- kunder som ikke har vært aktive i det siste 
- kunder som ofte samhandler med virksomheten din  

Hvis du har en detaljvirksomhet, kan du finne ut hvilke kunder som genererer størst omsetning, og belønne dem med en rabattkuponger. Du kan også identifisere tilfeldige kunder og tilby dem å delta i et belønningsprogram, slik at de oftere besøker bedriften.
Hvis du er i helsebransjen som leverer offentlige helsetjenester og målet er å redusere utgiftene for enkeltpasienter. En måte å gjøre dette på kan være å redusere regelmessige besøk ved å gi best mulig pleie i så få besøk som mulig. I dette tilfellet er målet å holde besøksfrekvensen lav og redusere regelmessige kostnader for pasientene. Du kan også identifisere segmenter av pasienter som har hyppige avtaler og høye regelmessige kostnader, og analysere disse sakene for å forbedre behandling av den enkelte. 

## <a name="required-data"></a>Obligatoriske data

Forslagene genereres basert på de valgte inndataene. 

- Kundeprofiler: Alle kunder eller medlemmer i et bestemt segment. 

- Tidsperiode: Siste måned, forrige år eller egendefinerte tidsrammer.

- Aktivitetstype: kjøp, detaljhandelstransaksjoner, elektroniske transaksjoner, kundestøttesaker, abonnementer og så videre.  

- Enhet i Customer Insights som inneholder aktivitetsdataene: UnifiedActivity-enheten eller enheten for en bestemt aktivitet. 

- Dimensjonene som skal inkluderes: Nylighet, hyppighet eller pengedimensjon, avhengig av forretningskravene.

## <a name="generate-suggested-segments"></a>Generer foreslåtte segmenter

1. Gå til **Segmenter**.

1. Velg fanen **Forslag (forhåndsversjon)**.

1. Velg **Finn nye forslag** og velg **Se eller forvent kundevirkemåte**. Velg **Start** for å kjøre den veiledede opplevelsen.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Første trinn i konfigurasjonsveiviseren for et foreslått segment basert på aktivitet.":::

1. Angi de nødvendige inndataene og velg **Neste** for å fortsette.

   - Velg kunder: Inkluder alle kunder eller et bestemt segment.
   - Velg aktivitet: Velg aktivitetstypen og enhetene som beskriver aktiviteten.
   - Innstillinger: Angi tidsperioden som skal vurderes, faktorer for forslag og tilordne attributtene.

1. Gå gjennom inndataene og velg **Kjør** for å kjøre modellen og generere forslag.

1. Det kan ta noen minutter å fullføre, avhengig av antall kundeprofiler og valgte aktiviteter. 

Når du har generert forslagene, kan du filtrere dem etter dimensjonen eller verdien du er mest interessert i. 

## <a name="view-details-of-a-suggested-segment"></a>Vis detaljer for et foreslått segment

Når forslagene er generert, finner du dem oppført i **Segmenter** > **Forslag (forhåndsversjon)** i delen **Aktivitetsbaserte forslag**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Utvidet siderute som viser detaljerte data for et foreslått segment.":::

Velg **Se forslag** i et foreslått segment for å vise detaljene for det segmentet. Sideruten inneholder detaljer som omfanget av hver dimensjon sammenlignet med målgruppen. Den fremhever også antall potensielle medlemmer i segmentet og den tilsvarende prosentandelen av totalkundene. Hvis du vil beholde forslaget som et segment, velger du **Opprett segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Lagre et forslag som et segment

1. Gå til **Segmenter** > **Forslag (forhåndsversjon)**.

1. Velg segmentet du vil lagre. 

1. Velg **Opprett segment** i sideruten. 

1. Når du har lagret segmentet, vises det i listen over segmenter i fanen **Alle segmenter**. Den kan nå [oppdateres eller slettes som alle andre segmenter](segments.md). Du kan ikke redigere segmentdetaljene. Du kan imidlertid endre inndatavilkårene for forslagene og generere ulike forslag.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Oppdater eller rediger et sett med forslag

1. Gå til **Segmenter** > **Forslag (forhåndsversjon)**, og se etter segmentet i delen **Aktivitetsbaserte forslag**.

1. Velg **Oppdater forslag** for å oppdatere forslagene samtidig som du beholder konfigurerte attributter. Du kan også velge **Rediger forslag** for å endre de konfigurerte attributtene. Systemet kjører prosessen på nytt, genererer segmentforslag basert på de nyeste dataene og erstatter de gjeldende forslagene.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
