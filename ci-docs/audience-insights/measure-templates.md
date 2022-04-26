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
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529413"
---
# <a name="use-a-template-to-build-a-measure"></a>Bruke en mal til å bygge et mål

Du kan bruke forhåndsdefinerte maler for vanlige [mål](measures.md) for å opprette dem. Detaljerte beskrivelser av malene og en veiledet opplevelse hjelper deg med effektiv måloppretting. Maler bygger på tilordnede data fra *Enhetlig aktivitet*-enheten. Sørg derfor for at du har konfigurert [kundeaktiviteter](activities.md) før du oppretter et mål fra en mal.

Hvis du vil opprette egendefinerte mål, kan du se [Bruk måleverktøyet til å opprette mål fra bunnen av](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrukere (B-til-C)](#tab/b2c)

Tilgjengelige målmaler: 
- Gjennomsnittlig transaksjonsverdi (ATV)
- Total transaksjonsverdi
- Gjennomsnittlig daglig omsetning
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

1. I delen **Angi tidsperiode** definerer du tidsrammen for dataene som skal brukes. Velg om du vil at det nye målet skal dekke hele datasett, ved å velge **Alle tider**, eller om du vil at målet skal fokusere på en **Bestemt tidsperiode**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Skjermbilde som viser tidsperiodedelen når du konfigurerer et mål fra en mal.":::

1. I den neste delen velger du **Legg til data** for å velge aktivitetene og tilordne de tilsvarende dataene fra enheten *Enhetlig aktivitet*.

    1. Trinn 1 av 2: Under **Aktivitetstype** velger du typen enhet du vil bruke. For **Aktiviteter** velger du enhetene du vil tilordne.
    1. Trinn 2 av 2: Velg attributtet fra enheten *Enhetlig aktivitet* for komponenten som kreves av formelen. For gjennomsnittlig transaksjonsverdi er det for eksempel attributtet som representerer transaksjonsverdien. For **Aktivitetstidsstempel** velger du attributtet fra enheten Enhetlig aktivitet som representerer datoen og klokkeslettet for aktiviteten.
   
1. Når datatilordningen er vellykket, kan du se statusen **Fullført** og navnet på de tilordnede aktivitetene og attributtene.

1. Du kan nå velge **Kjør** for å beregne resultatene av målet. Hvis du vil finjustere det senere, velger du **Lagre utkast**.

# <a name="business-accounts-b-to-b"></a>[Forretningsforbindelser (B-til-B)](#tab/b2b)

Denne funksjonen er bare tilgjengelig for tiltak som er opprettet i miljøer med individuelle kunder som primær målgruppe.

---
