---
title: Vise kundeprofiler
description: Få en kombinert visning av dine enhetlige kundedata.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596879"
---
# <a name="customer-profiles"></a>Kundeprofiler

**Kunder**-siden viser en kombinert visning av kundene, basert på profildata som samles inn fra [alle datakilder](data-sources.md). Kundeprofiler er tilgjengelige når du [oppretter den enhetlige kundeenheten](data-unification.md). Sørg for at du fullfører datasamlingsprosessen for å få rikere visninger av kundene. Du kan også bruke siden til å søke etter kunder.

Kunder kan være enkeltpersoner eller organisasjoner (forhåndsvisning). Hver kunde eller organisasjonsprofil representeres av en flis. Velg en flis for å vise ytterligere informasjon om den bestemte kunden eller organisasjonen. Bruk pagineringskontrollene nederst på siden for å vise flere oppføringer.

> [!div class="mx-imgBorder"] 
> ![B2C-kundeprofiler](media/profiles-customers.png "B2C-kundeprofiler")

Organisasjoner (forhåndsvisning)
> [!div class="mx-imgBorder"] 
> ![B2B-kundeprofiler](media/profile-customers-b2b.png "B2B-kundeprofiler")

> [!NOTE]
> Hvis du ikke kan se flisene når du velger **Kunder** i navigasjon, må administrator [definere minst ett søkbart attributt](search-filter-index.md) i **søk- og filterindeksen**.

## <a name="search-for-customers"></a>Søke etter kunder

Søk etter kunder ved å angi et navn eller et annet attributt i søkeboksen. Søket fungerer bare i kundeprofilenheten som ble opprettet i løpet av datasamlingsprosessen.

Som administrator kan du konfigurere de søkbare attributtene ved hjelp av siden **Søk- og filterindeks**. Du finner mer informasjon under [Behandle søk- og filterindeks](search-filter-index.md).

## <a name="filter-customers"></a>Filtrere kunder

Du kan filtrere kunder etter feltene i kundeprofilenheten. På samme måte som i søk må administratoren først definere feltene som filtrererbare ved hjelp av siden **Søk- og filterindeks**.

1. Velg **Filtrer** på **Kunder**-siden.

2. Merk av i boksene ved siden av attributtene du vil filtrere kunder etter.

   > [!div class="mx-imgBorder"] 
   > ![Kundeprofiler](media/profiles-customers3.png "Kundeprofiler")

3. Fjern filtrene ved å velge **Fjern filtre** på **Kunder**-siden.

##  <a name="customer-details-page"></a>Kundedetaljer-siden

Velg en hvilken som helst av kundeflisene for å åpne **Kundedetaljer**-siden. Denne visningen inneholder enhetlig informasjon om den valgte kunden.

Kundedetaljene inkluderer:

-   **Kundeprofilflis:** Denne flisen viser de forskjellige verdiene fra den enhetlige kundeprofilenheten. Disse detaljene kan omfatte e-postadresse, navn, poststed og så videre. 

-   **Potensielle interesser, potensielle merker:** Viser om du har konfigurert en førsteparts supplering. Det representerer potensielle interesser og tiltrekning for merker en kunde med en profil som ligner på denne kunden, kan ha. Hvis du vil ha mer informasjon, kan du se [Supplere kundeprofiler med merke- og interesseaffiniteter](enrichment-microsoft-graph.md).

-   **Mål:** Viser om du har konfigurert ett eller flere mål for en bestemt type: kundeattributtmål. De inkluderer beregnede KPI-er rundt kundene på det enkelte kundenivået. Hvis du vil ha mer informasjon, kan du se [Definere og behandle mål](measures.md).

-   **Aktivitetstidslinje:** Vises om du har konfigurert aktiviteter. Tidslinjevisningen inneholder kronologisk sorterte aktiviteter av denne kunden, og starter med den nyeste aktiviteten. Hvis du vil ha mer informasjon, kan du se [Kundeaktiviteter](activities.md).

Velg **Tilbake til Kunder** for å gå tilbake til kundesøkesiden.

## <a name="next-steps"></a>Neste trinn

[Legge til flere datakilder](data-sources.md) eller [opprette kundesegmenter](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]