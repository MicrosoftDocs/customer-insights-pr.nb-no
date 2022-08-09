---
title: Foreslåtte segmenter basert på mål (forhåndsversjon)
description: La maskinlæring hjelpe deg med å finne nye og interessante segmenter basert på kundeattributter.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170969"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Foreslåtte segmenter basert på mål (forhåndsversjon)

Oppdag interessante segmenter av kundene ved hjelp av en modell for kunstig intelligens. Denne maskinlæringsfunksjonen foreslår segmenter basert på mål eller kundeattributter. Det kan bidra til å forbedre KPI-ene (nøkkelindikatorene) eller bedre forstå innflytelsen til attributter i sammenheng med andre attributter.

> [!NOTE]
> Funksjonen for foreslåtte segmenter bruker automatiske metoder til å evaluere data og lage prediksjoner basert på dataene. Den kan derfor brukes som en metode for profilering, slik denne termen er definert i EUs personvernforordning (GDPR). Din bruk av denne funksjonen til å behandle data kan være underlagt GDPR eller andre lover eller forskrifter. Du er ansvarlig for å sikre at bruken av Dynamics 365 Customer Insights, inkludert denne funksjonen, samsvarer med alle gjeldende lover og bestemmelser, inkludert lover som er relatert til personvern, personopplysninger, biometriske data, databeskyttelse og konfidensialitet for kommunikasjon.

:::image type="content" source="media/suggested-segments.png" alt-text="Foreslåtte segmenter-side som viser detaljer om et forslag i en siderute.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Foreslåtte segmenter for å forbedre KPI-ene

Hvis du bruker [opprettede mål](measures.md) til å spore KPI-ene, oppretter du segmenter for å vise innflytelsen på KPI-en. Du kan bruke denne informasjonen til å kjøre en svært målrettet kampanje.

Du sporer for eksempel et mål kalt *TotalSpendPerCustomer*. Som virksomhet ønsker du å se at dette tallet vokser. Når du velger et mål som hovedattributt, velger du attributtene du vil vurdere for innflytelse. La oss si *medlemskapsnivå*, *medlemskapsperiode* og *yrke*. Customer Insights kan deretter foreslå et segment som forteller deg hvem som er den største innflytelsen til dette målet. *Regnskapsførere* som er *Gold*-medlemmer, og som har vært med i virksomheten i *minst fem år*, er for eksempel den største påvirkeren av *TotalSpendPerCustomer*. Du får en beregnet segmentstørrelse for hvert forslag. Du kan bruke denne informasjonen til å opprette kampanjer for målgruppene.

## <a name="understand-what-influences-a-customer-attribute"></a>Forstå hva som har innvirkning på et kundeattributt

Du kan velge et kundeattributt i stedet for et mål som hovedattributt. Basert på valget av innflytelsesattributter oppretter modellen for kunstig intelligens en rekke forslag som viser hvordan de valgte attributtene har innflytelse på hovedattributtet.

Du velger for eksempel *Belønningsmedlem (Ja/Nei)* som hovedattributt. *Anseelse*, *Yrke* og *Antall støtteforespørsler* angis som andre attributter for innflytelse. Modell for kunstig intelligens kan foreslå segmenter som for det meste indikerer at IT-profesjonelle med periode over to år, er belønningsmedlemmer. Et annet forslag kan trekke frem at regnskapsførere med anseelse over ett år og færre enn tre støtteforespørsler, er belønningsmedlemmer.

## <a name="artificial-intelligence-usage"></a>Bruk av kunstig intelligens

Ved hjelp av hovedattributtet og innflytelsesattributtene foreslår en beslutningstrealgoritme interessante segmenter. Forslagene er basert på regler eller mønstre som ble plukket opp av AI-algoritmen. Bare segmenter som er betydelig forskjellige fra den gjennomsnittlige populasjonen, vises som forslag. Sammenligningen med den gjennomsnittlige populasjonen er basert på det valgte målet eller hovedattributtet.

### <a name="responsible-ai"></a>Ansvarlig kunstig intelligens

Med foreslåtte segmenter velger du attributter for å opprette nye segmenter og behandle dataene du velger. Når du velger attributter, inkludert sensitive attributter som rase, legning eller kjønn, må du sørge for at du kan og bør behandle disse dataene. Du er ansvarlig for å overholde eventuelle lover som gjelder for organisasjonen din, og overholde organisasjonens prinsipper og personvernpolicyer.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Forskjellige resultater for hovedattributter med kategoriske og numeriske verdier

Segmentforslag er forskjellige hvis du velger et numerisk attributt eller et kategorisk attributt som hovedattributt. Verdier i et kategorisk attributt inneholder to eller flere kategorier eller typer. Et numerisk attributt inneholder kvantitative data og har en tilknyttet målemetode.

Med et numerisk attributt som *årlig inntekt* eller *medlemsperiode* som hovedattributt foreslår systemet segmenter som har en høyere eller lavere gjennomsnittlig verdi av det numeriske attributtet sammenlignet med alle kunder.

Et kategorisk attributt som *kundetilfredshet* som hovedattributtet resulterer i foreslåtte segmenter som har en høyere eller lavere prosentandel av kunder som tilhører en bestemt kategori, sammenlignet med prosentandelen av alle kunder som tilhører den samme kategorien. *Kundetilfredshet* velges for eksempel som hovedattributt, og det består av tre kategorier  (*Lav*, *Middels* og *Høy*). For hver kategori foreslås det segmenter som har en høyere eller lavere prosentandel av kundene som tilhører den kategorien, sammenlignet med andelen av alle kunder i den samme kategorien. Hvis 22 % av alle kunder er *svært* fornøyde, foreslås det bare segmenter som har en høyere eller lavere andel av kundene med *høy* kundetilfredshet sammenlignet med 22 % for den kategorien. Segmenter foreslås på samme måte for hver av de andre kategoriene (*Lav* og *Middels*) hvis de er statistisk signifikante.

> [!NOTE]
> For øyeblikket støtter vi bare primære kategoriske attributter som har opptil ti kategorier. Hvis du vil se segmentforslag basert på et hovedattributt med mer enn ti kategorier, anbefaler vi at du grupperer noen av kategoriene for å redusere antall kategorier til ti eller færre. Denne begrensningen gjelder bare for hovedattributter. For å påvirke kategoriske attributter støtter vi for øyeblikket maksimalt 100 kategorier.

## <a name="generate-suggested-segments"></a>Generer foreslåtte segmenter

1. Gå til **Segmenter**, og velg fanen **Forslag (forhåndsversjon)**.

1. Velg **Søk etter nye forslag**, og velg **Forbedre et mål / en beregning**. Velg **Start**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Velg forbedre et mål for de foreslåtte segmentene.":::

1. Velg et kundeattributt eller mål som hovedattributt, og velg **Neste**.

1. Velg innflytelsesattributtene, og velg **Kjør**.

   > [!TIP]
   > Hvis du velger flere innflytelsesattributter, øker sjansene for å evaluere hvordan de har innflytelse på hovedattributtet. Ikke inkluder attributter som ikke har noen innflytelse på hovedattributtet. Hvis for eksempel alle kundene kommer fra et bestemt land, må du ikke inkludere attributtet *land* fordi det ikke vil ha noen innvirkning på utdataene.

Avhengig av antall kundeprofiler og valgte attributter, kan det ta noen minutter å behandle de valgte attributtene.

## <a name="manage-suggested-segments"></a>Administrer foreslåtte segmenter

Gå til **Segmenter**, og velg fanen **Forslag (forhåndsvisning)**. I delen **Attributtbasert segmentforslag** velger du et foreslått segment for å vise tilgjengelige handlinger.

- **Vis** detaljene om det foreslåtte segmentet og attributtverdiene eller reglene som modellen for kunstig intelligens har lært.
- Velg **Lagre som segment** for å lagre forslaget som et segment. Det vises i fanen **Alle segmenter** og kan [oppdateres, redigeres eller slettes](segments.md).
- **Rediger attributter** og endre de konfigurerte attributtene som erstatter de gjeldende forslagene.
- **Oppdater forslag** for å oppdatere forslagene samtidig som du beholder konfigurerte attributter.

## <a name="limitations"></a>Begrensninger

1. Manglende samsvar mellom beregnet segmentstørrelse: Hvis du velger et hovedattributt som inneholder tomme verdier, kan det påvirke den beregnede segmentstørrelsen i segmentforslagene. Når du lagrer et slikt segment, kan den faktiske segmentstørrelsen være forskjellig fra den opprinnelige beregning.

2. Hovedattributter av boolsk type fungerer ikke: For øyeblikket støtter vi bare strenger og numeriske typer data som hovedattributt.

3. Foreslåtte segmenter er ikke tydelige nok: Husk at de valgte attributtene og distribusjonen av verdier for disse attributtene har innflytelse på resultatene. Du kan endre innflytelsesattributtene eller hovedattributtet for å få andre resultater.

[!INCLUDE [footer-include](includes/footer-banner.md)]