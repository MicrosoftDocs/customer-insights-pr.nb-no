---
title: Velg kildefelter for datasamling
description: Det første trinnet i samlingsprosessen er å velge enheter, attributter, primærnøkler og semantiske typer for å tildele data til den enhetlige kundeprofilen.
recommendations: false
ms.date: 08/12/2022
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
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304577"
---
# <a name="select-source-fields-for-data-unification"></a>Velg kildefelter for datasamling

Det første trinnet i samlingen er å velge enhetene og feltene i datasettene du vil samle. Velg enheter som inneholder kunderelaterte detaljer, for eksempel navn, adresse, telefonnummer og e-post. Du kan velge ett eller flere enheter.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Velg enheter og felt

1. Gå til **Data** > **Samle**.

   For enkeltkunder (B2C) vises **Samle**-målsiden med **Kom i gang** i første trinn, **Kildefelter**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Skjermbilde av målsiden for samling for første kjøreopplevelse for enkeltkunder.":::

   For forretningskontoer (B2B) vises **Samle**-målsiden med **Samle forretningsforbindelser** og **Kom i gang** i første trinn, **Kildefelter**. Trinnene **Samle kontakter (forhåndsversjon)** er valgfrie og venter på fullføring av forretningsforbindelsessamling.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Skjermbilde av målsiden for samling for første kjøreopplevelse for forretningskontoer.":::

1. Velg **Komme i gang**.

1. Velg **Velg enheter og felter** på **Kildefelter**-siden. Ruten **Velg enheter og felter** vises.

1. Velg minst én enhet.

1. For hver valgte enhet identifiserer du feltene du vil bruke for å samsvare kundeoppføringer og felter som skal inkluderes i den enhetlige profilen. Disse feltene kalles *attributter*. Du kan velge de obligatoriske attributtene individuelt fra en enhet, eller inkludere alle attributter fra en enhet ved å merke av i avmerkingsboksen på enhetsnivå. Du kan søke i nøkkelord på tvers av alle attributter og enheter for å velge de nødvendige attributtene du vil tilordne.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Skjermbilde av valgte enheter og attributter.":::

   I dette eksemplet skal vi legge til enhetene **eCommerceContacts** og **loyCustomer**. Ved å velge disse enhetene kan du avlede innsikt om hvilke av de elektroniske forretningskundene som er medlemmer av loyalitetsprogrammet.

1. Velg **Bruk** for å bekrefte valgene. De valgte enhetene og attributtene vises.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Velg primærnøkkel og semantisk type for attributter

   :::image type="content" source="media/m3_select_primary.png" alt-text="Skjermbilde av valgte enheter med primærnøkkel ikke valgt ennå." lightbox="media/m3_select_primary.png":::

Utfør trinnene nedenfor for hver enhet.

1. Velg **primærnøkkelen**. Primærnøkkelen er et attributt som er unikt for enheten. For at et attributt skal være en gyldig primærnøkkel, bør den ikke inneholde duplikate verdier, manglende verdier eller nullverdier. Datatypeattributtene streng, heltall og GUID støttes som primærnøkler.

1. Hvis du vil bruke modeller for kunstig intelligens for smart prediksjon av semantikk, som sparer tid og forbedrer nøyaktigheten, sørger du for at **Intelligent tilordning** er aktivert. Intelligent tilordning gir AI-basert semantikkanbefalinger i **Type**-feltet.

1. For hvert attributt velger du en semantisk **type** som best beskriver dette attributtet, for eksempel navn, poststed eller e-postadresse.

   > [!NOTE]
   > I B2C må ett felt tilordnes til den semantiske typen *Person.FullName* for å fylle ut kundenavnet på kundekortet. I B2B må navnet på forretningsforbindelsen tilordnes til *Organization.Name*. Ellers vises kundekortene uten navn.

   1. Velg et annet alternativ for å overstyre en attributtype identifisert av systemet. Hvis typen ikke finnes, oppretter du en egendefinert semantisk type ved å velge **Type**-feltet for attributtet og skrive inn det egendefinerte navnet på den semantiske typen.

   1. Hvis du vil legge til et attributt som inneholder en nettadresse til offentlig tilgjengelige profilbilder eller logoer, velger du enheten og feltet som inneholder nettadressen. I **Type**-feltet angir du følgende:
      - For en person: Person.ProfileImage
      - For en organisasjon: Organization.LogoImage

1. Se gjennom attributtene der en semantisk type identifiseres automatisk. Disse attributtene vises under **Se gjennom tildelte felter**. Bare attributter av samme type kan kombineres i trinnet **Samle kundefelter**. Semantiske typer brukes til automatisk å foreslå innsikt. Kontroller at typene du velger, er konsekvente for alle de valgte enhetene.

1. For attributter som ikke tildeles automatisk til en semantisk type, velger du et semantisk felt, angir det egendefinerte attributtypenavnet eller lar dem være ikke tildelt. Disse attributtene vises under **Definer dataene i de ikke tildelte feltene**.

1. Når du har fullført trinnene for hver enhet, velger du **Lagre kildefelter**.

1. Velg **Neste**.

> [!div class="nextstepaction"]
> [Neste trinn: Fjern duplikater](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
