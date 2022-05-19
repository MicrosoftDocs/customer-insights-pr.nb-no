---
title: Velg kildefelter for datasamling
description: Det første trinnet i samlingsprosessen er å velge enheter, attributter, primærnøkler og semantiske typer for å tildele data til den enhetlige kundeprofilen.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741007"
---
# <a name="select-source-fields-for-data-unification"></a>Velg kildefelter for datasamling

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Det første trinnet i samlingen er å velge enhetene og feltene i datasettene du vil samle. Velg enheter som inneholder kunderelaterte detaljer, for eksempel navn, adresse, telefonnummer og e-post. Du kan velge ett eller flere enheter.

## <a name="select-entities-and-fields"></a>Velg enheter og felt

1. Gå til **Data** > **Samle**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Skjermbilde av målsiden for samling for første kjøreopplevelse med Kom i gang uthevet.":::

1. Velg **Komme i gang**.

1. Velg **Velg enheter og felter** på **Kildefelter**-siden. Ruten **Velg enheter og felter** vises.

1. Velg minst én enhet.

1. For hver valgte enhet identifiserer du feltene du vil bruke for å samsvare kundeoppføringer og felter som skal inkluderes i den enhetlige profilen. Disse feltene kalles *attributter*. Du kan velge de obligatoriske attributtene individuelt fra en enhet, eller inkludere alle attributter fra en enhet ved å merke av i avmerkingsboksen på enhetsnivå. Du kan søke i nøkkelord på tvers av alle attributter og enheter for å velge de nødvendige attributtene du vil tilordne.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Skjermbilde av valgte enheter og attributter.":::

   I dette eksemplet skal vi legge til enhetene **Kontakter** og **CustomerLoyalty**. Ved å velge disse enhetene kan du avlede innsikt om hvilke av de elektroniske forretningskundene som er medlemmer av loyalitetsprogrammet.

1. Velg **Bruk** for å bekrefte valgene. De valgte enhetene og attributtene vises.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Velg primærnøkkel og semantisk type for attributter

   :::image type="content" source="media/m3_select_primary.png" alt-text="Skjermbilde av valgte enheter med primærnøkkel ikke valgt." lightbox="media/m3_select_primary.png":::

Utfør trinnene nedenfor for hver enhet.

1. Velg **primærnøkkelen**. Primærnøkkelen er et attributt som er unikt for enheten. For at et attributt skal være en gyldig primærnøkkel, bør den ikke inneholde duplikate verdier, manglende verdier eller nullverdier. Datatypeattributtene streng, heltall og GUID støttes som primærnøkler.

1. Hvis du vil bruke modeller for kunstig intelligens for smart prediksjon av semantikk, kan du spare tid og forbedre nøyaktigheten ved å sørge for at **Intelligent tildeling** er på. Intelligent tilordning fremhever AI-basert semantikkanbefaling i **Type**-feltet. Du kan overstyre det foreslåtte valget ved å velge en hvilken som helst semantisk type fra den tilgjengelige listen over alternativer.

1. For hvert attributt velger du en semantisk **type** som best beskriver dette attributtet, for eksempel navn, poststed eller e-postadresse.

   > [!NOTE]
   > Ett felt må tildeles til semantisk type *Person.FullName* for å fylle ut kundenavnet på kundekortet. Ellers vises kundekortene uten navn.

   1. Velg en annen type for å endre en attributtype identifisert av systemet. Hvis typen ikke finnes, oppretter du en egendefinert semantisk type ved å velge **Type**-feltet for attributtet og skrive inn det egendefinerte navnet på den semantiske typen.

   1. Hvis du vil legge til et attributt som inneholder en nettadresse til offentlig tilgjengelige profilbilder eller logoer, velger du enheten og feltet som inneholder nettadressen. I **Type**-feltet angir du følgende:
      - For en person: Person.ProfileImage
      - For en organisasjon: Organization.LogoImage

   1. Angi Organization.Name i **Type**-feltet for et attributt for et navneattributt for konto.

1. Se gjennom attributtene der en semantisk type identifiseres automatisk. Disse attributtene vises under **Se gjennom tildelte felter**. Bare attributter av samme type kan kombineres i trinnet **Enhetlige kundefelter**. Semantiske typer brukes til automatisk å foreslå innsikt. Kontroller at typene du velger, er konsekvente for alle de valgte enhetene.

1. For attributter som ikke tildeles automatisk til en semantisk type, velger du et semantisk felt, angir det egendefinerte attributtypenavnet eller lar dem være ikke tildelt. Disse attributtene vises under **Definer dataene i de ikke tildelte feltene**.

1. Når du har fullført trinnene for hver enhet, velger du **Lagre kildefelter**.

1. Velg **Neste**.

> [!div class="nextstepaction"]
> [Neste trinn: Fjern duplikater](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
