---
title: Opprett mål fra maler
description: Definer tiltak ved hjelp av maler for vanlige brukssaker.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170785"
---
# <a name="create-measures-from-templates"></a>Opprett mål fra maler

Bruk forhåndsdefinerte maler for vanlige [mål](measures.md) for å opprette dem. Maler bygger på tilordnede data fra *Enhetlig aktivitet*-enheten. Sørg derfor for at du har konfigurert [kundeaktiviteter](activities.md) før du oppretter et mål fra en mal.

Målmaler støttes bare i miljøer for **enkeltkunder**. Hvis du vil opprette egendefinerte mål eller opprette mål for B2B, kan du se [Bruk måleverktøyet](measure-builder.md).

Tilgjengelige målmaler:
- Gjennomsnittlig transaksjonsverdi (ATV)
- Total transaksjonsverdi
- Gjennomsnittlig daglig omsetning
- Gjennomsnittlig månedlig omsetning
- Gjennomsnittlig årlig omsetning
- Transaksjonstelling
- Opptjente fordelspoeng
- Innløste fordelspoeng
- Saldo for fordelspoeng
- Levetid for aktiv kunde
- Varighet for fordelsmedlemskap
- Tid siden forrige kjøp

## <a name="build-a-new-measure-using-a-template"></a>Bygg et nytt mål ved hjelp av en mal

1. Gå til **Mål**.

1. Velg **Ny** og deretter **Velg en mal**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Skjermbilde av rullegardinmenyen når du oppretter et nytt mål med utheving på mal.":::

1. Finn malen du ønsker, og velg **Velg mal**.

1. Se gjennom de nødvendige dataene, og velg **Kom i gang** hvis du har alle dataene på plass.

1. Velg **Rediger detaljer** ved siden av Målnavn. Oppgi et navn for målet. Du kan eventuelt legge til [merker](work-with-tags-columns.md#manage-tags) i målet.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogboksen Rediger detaljer.":::

1. Velg **Ferdig**.

1. I delen **Angi tidsperiode** definerer du tidsrammen for dataene. Velg om du vil at det nye målet skal dekke hele datasett, ved å velge **Alle tider**, eller om du vil at målet skal fokusere på en **Bestemt tidsperiode**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Skjermbilde som viser tidsperiodedelen når du konfigurerer et mål fra en mal.":::

1. I den neste delen velger du **Legg til data** for å velge aktivitetene og tilordne de tilsvarende dataene fra enheten *Enhetlig aktivitet*.

    1. Trinn 1 av 2: Under **Aktivitetstype** velger du typen enhet du vil bruke. For **Aktiviteter** velger du enhetene du vil tilordne, og deretter velger du **Neste**.
    1. Trinn 2 av 2: Velg attributtet fra enheten *Enhetlig aktivitet* for komponenten som kreves av formelen. For gjennomsnittlig transaksjonsverdi er det for eksempel attributtet som representerer transaksjonsverdien. For **Aktivitetstidsstempel** velger du attributtet fra enheten *Enhetlig aktivitet* som representerer datoen og klokkeslettet for aktiviteten.
    1. Velg **Lagre**.

    Når datatilordningen er vellykket, vises statusen **Fullført** og navnet på de tilordnede aktivitetene og attributtene.

1. Velg **Kjør** for å beregne resultatene av målet. Velg **Lagre utkast** hvis du vil beholde gjeldende konfigurasjon og kjøre målet senere. **Mål**-siden vises.

## <a name="next-step"></a>Neste trinn

Bruk eksisterende målinger til å opprette [et kundesegment](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
