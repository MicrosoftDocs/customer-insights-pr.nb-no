---
title: Tilordne enheter og attributter for dataforening
description: Velg enheter, attributter, primærnøkler og semantiske typer for å tilordne data til den enhetlige kundeprofilen.
ms.date: 10/18/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
ms.openlocfilehash: 7ee3feea8423f35f32ff471b3ed8eb3447584089
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648174"
---
# <a name="map-entities-and-attributes"></a>Tilordne enheter og attributter

**Tilordning** er første trinn i dataforeningsprosessen i målgruppeinnsikt. Tilordning består av tre faser:

- *Valg av enhet*: Identifiser de enhetene som kan kombineres, som fører til et datasett med mer fullstendig informasjon om kundene.
- *Attributtvalg*: For hver enhet identifiserer du kolononnene du vil kombinere, og avstemmer i fasene for *samsvar* og *sammenslåing*. Disse kolonnene kalles *attributter*.
- *Hovednøkkel og valg av semantisk type*: For hver enhet angir du et attributt du vil definere som primærnøkkel for enheten, og identifiser en semantisk type som best beskriver attributtet, for hvert attributt.

Hvis du vil ha mer informasjon om den generelle flyten for datasamling, se [Samle](data-unification.md).

## <a name="select-the-first-entities"></a>Velge de første enhetene

1. I Målgruppeinnsikt går du til **Data** > **Samle** > **Tilordne**.

2. Start tilordningsfasen ved å velge **Velg enheter**.

3. Velg enhetene og attributtene du vil bruke i *samsvars*- og *sammenslåings*-fasene. Du kan velge obligatoriske attributter enkeltvis fra en enhet eller inkludere alle attributter fra en enhet ved å merke av for **Inkluder alle felt** på enhetsnivå. Vi anbefaler at du velger minst to enheter for å dra nytte av datasamlingsprosessen.

   > [!div class="mx-imgBorder"]
   > ![Legg til enhet-eksempel.](media/data-manager-configure-map-add-entities-example.png "Legg til enhet-eksempel")

   I dette eksemplet skal vi legge til enhetene **eCommerceContacts** og **loyCustomers**. Ved å velge disse enhetene kan du avlede innsikt om hvilke av de elektroniske forretningskundene som er medlemmer av loyalitetsprogrammet.
   
   Du kan søke i nøkkelord på tvers av alle attributter og enheter for å velge de nødvendige attributtene du vil tilordne.
   
     > [!div class="mx-imgBorder"]
   > ![Eksempler på søkefelt.](media/data-manager-configure-map-search-fields-example.png "Eksempler på søkefelt")

4. Velg **Bruk** for å bekrefte valgene.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Velg primærnøkkel og semantisk type for attributter

Etter at du har valgt enhetene, viser **Tilordne**-siden de valgte enhetene for gjennomgang. Definer primærnøkkelen for en enhet, og identifiser den semantiske typen for et attributt i enheten.

- **Primærnøkkel**: Velg ett attributt som primærnøkkel for hver av enhetene. For at et attributt skal være en gyldig primærnøkkel, bør den ikke inneholde duplikate verdier, manglende verdier eller nullverdier. Attributter for datatypen streng, heltall og GUID støttes som primærnøkler, og vises i et felt du kan velge fra.

- **Semantisk type for attributt**: Kategorier av attributter, for eksempel e-postadresse eller navn. Hvis du vil bruke AI-modeller for smart prediksjon av semantikk, spare tid og forbedre nøyaktigheten, angir du **Intelligent tilordning** til **På**. Intelligent tilordning fremhever AI-basert semantikkanbefaling i **Type**-feltet. Hvis du setter den til **AV**, vil du se våre vanlige tilordningsanbefalinger. Du kan velge en hvilken som helst semantisk type fra den tilgjengelige listen over alternativer og overstyre det foreslåtte valget.

> [!div class="mx-imgBorder"]
> ![Attributtype og semantisk prediksjon.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attributtype og semantisk prediksjon")

Det er også mulig å legge til en egendefinert semantisk type. Velg typefeltet for et attributt, og skriv inn det egendefinerte semantiske typenavnet. På denne måten kan du også endre attributtypene som ble identifisert av systemet.

Alle attributter som en semantisk type identifiseres for, grupperes automatisk i delen **Se gjennom tilordnede felt**. Se gjennom disse attributtene og de semantiske typene fordi de blir brukt til å kombinere enhetene i flettingstrinnet i datasamling.

Attributter som ikke tilordnes automatisk til en semantisk type, grupperes i delen **Definer dataene i feltene som ikke er tilordnet**. Velg feltet for semantisk type for attributter som ikke er tilordnet, eller skriv inn det egendefinerte navnet på attributtet.

> [!div class="mx-imgBorder"]
> ![Primærnøkkel og attributtype.](media/data-manager-configure-map-add-attributes.png "Primærnøkkel og attributtype")

> [!NOTE]
> Ett felt må være tilordnet den semantiske typen Person.FullName for å fylle ut kundenavnet i kundekortet. Ellers vises kundekortene uten navn. 

## <a name="add-and-remove-attributes-and-entities"></a>Legge til og fjerne attributter og enheter

1. På **Samle** > **Tilordne** velger du **Rediger felt**.

2. Legg til eller Fjern attributter og enheter i **Rediger felt**-ruten. Bruk søket eller rull for å finne og velge ønskede attributter og enheter. Du kan ikke fjerne et attributt eller en enhet hvis de allerede er samsvart.

   > [!div class="mx-imgBorder"]
   > ![Legg til eller fjern attributter.](media/configure-data-map-edit.png "Legge til eller fjerne attributter")

3. Velg **Bruk**.

## <a name="add-images-to-profiles"></a>Legge til bilder i profiler

Hvis en enhet inneholder URL-adresser til offentlig tilgjengelige profilbilder eller logoer, kan du legge dem til i den enhetlige kundeprofilen.

Velg enheten, og finn feltet som inneholder URL-adressen til profilbildet. Skriv inn følgende verdi manuelt i **Type**-inndatafeltet: 
- For en person: Person.ProfileImage
- For en organisasjon: Organization.LogoImage

Fortsett med samlingstrinnene, og kontroller at attributtet som inneholder bilde-URL-adressen, også legges til i [flettings](merge-entities.md)-trinnet.

## <a name="set-attributes-for-organizations"></a>Angi attributter for organisasjoner

For organisasjoner (forhåndsvisning) må attributtypen tilordnes "Organization.Name"
> [!div class="mx-imgBorder"]
> ![Primærnøkkel og attributtype B2B](media/configure-data-map-edit-b2b.png "Primærnøkkel og attributtype B2B")

## <a name="next-step"></a>Neste trinn

Som en del av datasamlingsprosessen går du til **Samsvar**-siden. Gå [**Samsvar**](match-entities.md) for å lære om dette trinnet.

> [!TIP]
> Se følgende video: [Komme i gang: Opprette en enhetlig kundeprofil](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]