---
title: Samle kunde- eller kontofelter
description: Slå sammen enheter for å opprette enhetlige kundeprofiler.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 78e2528d4a3058f879d83952f72ed88a1da065b6
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740869"
---
# <a name="unify-customer-fields"></a>Samle kundefelter

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

I dette trinnet i samlingsprosessen velger og utelater du attributter som skal flettes inn i enheten for den enhetlige profilen. Hvis for eksempel tre enheter hadde e-postdata, vil du kanskje beholde alle tre separate e-postfelter eller slå dem sammen til ett enkelt e-postfelt for den enhetlige profilen. Noen attributter kombineres automatisk av systemet. Du kan opprette stabile og unike kunde-ID-er og gruppere relaterte profiler i en klynge.

:::image type="content" source="media/m3_unify.png" alt-text="Slå sammen-siden i dataforeningsprosessen som viser tabell med sammenslåtte felter som definerer den enhetlige kundeprofilen.":::

## <a name="review-and-update-the-customer-fields"></a>Se gjennom og oppdater kundefeltene

1. Se gjennom listen over felter som skal samles i fanen **Kundefelter** i tabellen. Gjør eventuelle endringer.

   1. For kombinerte felter kan du:
      - [Rediger](#edit-a-merged-field)
      - [Gi nytt navn](#rename-fields)
      - [Separat](#separate-merged-fields)
      - [Ekskluder](#exclude-fields)
      - [Flytt opp eller ned](#change-the-order-of-fields)

   1. For enkeltfelter kan du:
      - [Kombiner felt](#combine-fields-manually)
      - [Slå sammen en gruppe felter](#combine-a-group-of-fields)
      - [Gi nytt navn](#rename-fields)
      - [Ekskluder](#exclude-fields)
      - [Flytt opp eller ned](#change-the-order-of-fields)

1. [Generer eventuelt konfigurasjon av kunde-ID](#configure-customer-id-generation).

1. [Grupper eventuelt profiler i husholdninger eller klynger](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Neste trinn: Se gjennom samlingen](review-unification.md)

### <a name="edit-a-merged-field"></a>Rediger et sammenslått felt

1. Velg et flettet felt og velg **Rediger**. Ruten Kombiner felter vises.

1. Angi hvordan du vil kombinere eller flette feltene fra et av tre alternativer:
    - **Viktighet**: Identifiserer vinnerverdien basert på viktighetsrangering angitt for de deltagende feltene. Dette er standardalternativet for sammenslåing. Velg **Flytt opp/ned** for å angi viktighetsrangering.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Viktighetsalternativ i dialogboksen for flettefelter.":::

    - **Nyeste**: Identifiserer vinnerverdien basert på mest nylige. Krever en dato eller et numerisk felt for hver enhet som deltar i omfanget for flettefeltene, for å definere nyligheten.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Nylighetsalternativ i dialogboksen for flettefelter.":::

    - **Minst nylig**: Identifiserer vinnerverdien basert på minste nylighet. Krever en dato eller et numerisk felt for hver enhet som deltar i omfanget for flettefeltene, for å definere nyligheten.

1. Du kan legge til flere felt for å delta i fletteprosessen.

1. Du kan gi nytt navn til det flettede feltet.

1. Velg **Ferdig** for å ta i bruk endringene.

### <a name="rename-fields"></a>Endre navn på felt

Endre visningsnavn for flettede eller separate felter. Du kan ikke endre navnet på utdataenheten.

1. Merk feltet og velg **Endre navn**.

1. Skriv inn det nye visningsnavnet.

1. Velg **Ferdig**.

### <a name="separate-merged-fields"></a>Del sammenslåtte felter

Du skiller sammenslåtte felter ved å finne attributtet i tabellen. Delte felter vises som individuelle datapunkter i den enhetlige kundeprofilen.

1. Velg det flettede feltet, og velg **Separate felter**.

1. Bekreft delingen.

### <a name="exclude-fields"></a>Utelat felter

Utelat et sammenslått eller separat felt fra den enhetlige kundeprofilen. Hvis feltet brukes i andre prosesser, for eksempel i et segment, fjerner du det fra disse prosessene før du utelater det fra kundeprofilen.

1. Velg et felt og velg **Utelat**.

1. Bekreft utelatelsen.

Velg **Utelatte felter** for å vise listen over alle utelatte felter. Du kan om nødvendig legge til det utelatte feltet igjen.

### <a name="change-the-order-of-fields"></a>Endre rekkefølgen på feltene

Noen enheter inneholder flere detaljer enn andre. Hvis en enhet inneholder de nyeste dataene om et felt, kan du prioritere det over andre enheter ved å slå sammen verdier.

1. Velg feltet.
  
1. Velg **Flytt opp/ned** for å angi rekkefølgen, eller flytt og slipp dem i ønsket posisjon.

### <a name="combine-fields-manually"></a>Slå sammen felter manuelt

Kombiner separate felter for å opprette et flettet attributt.

1. Velg **Kombiner** > **Felter**. Ruten Kombiner felter vises.

1. Angi vinnerregelen for sammenslåing i **Kombiner felter etter** rullegardinmenyen.

1. Velg **Legg til felt** for å kombinere flere felter.

1. Angi et **navn** og et **navn på utdatafelt**.

1. Velg **Ferdig** for å ta i bruk endringene.

### <a name="combine-a-group-of-fields"></a>Slå sammen en gruppe felter

Behandle en gruppe felter som én enkelt enhet. Hvis oppføringene for eksempel inneholder feltene Adresse 1, Adresse2, Poststed og Poststed, vil vi ikke slå sammen adresse2 for en annen oppføring, og vi tror at dataene blir mer fullstendige.

1. Velg **Kombiner** > **Gruppe med felter**.

1. Angi vinnerregelen for sammenslåing i **Ranger grupper etter**-rullegardinlisten.

1. Velg **Legg til**, og velg om du vil legge til flere felter eller grupper i feltene.

1. Angi et **navn** og et **utdatanavn** for hvert kombinerte felt.

1. Oppgi et **navn** for gruppen felter.

1. Velg **Ferdig** for å ta i bruk endringene.

## <a name="configure-customer-id-generation"></a>Konfigurer kunde-ID-generering

Definer hvordan kunde-ID-verdier skal genereres, de unike kundeprofilidentifikatorene. Trinnet for samle felter i datasamlingsprosessen genererer den unike kundeprofilidentifikatoren. Identifikatoren er *CustomerId* i *Kunde*-enheten som er et resultat av dataenhetsprosessen.

*CustomerId* basert på et hash-nummer for den første verdien i primærnøklene som ikke er nullvinner. Disse nøklene kommer fra enhetene som brukes i datasamlingen, og påvirkes av samsvarsrekkefølgen.Den genererte kunde-ID-en kan derfor endres når en primærnøkkelverdi endres i hovedenheten i samsvarsordren. Primærnøkkelverdien representerer kanskje ikke alltid samme kunde.

Konfigurasjon av en stabil kunde-ID gjør det mulig å unngå denne virkemåten.

1. Velg kategorien **Nøkler**.

1. Hold markøren på **CustomerId**-raden og velg **Konfigurer**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontroller for å tilpasse ID-genereringen.":::

1. Velg opptil fem felter som vil bestå av en unik kunde-ID og er mer stabil. Oppføringer som ikke samsvarer med konfigurasjonen, bruker i stedet en systemkonfigurert ID.  

1. Velg **Ferdig**.

## <a name="group-profiles-into-households-or-clusters"></a>Grupper profiler i husholdninger eller klynger

Du kan definere regler for å gruppere relaterte profiler i en klynge. Det finnes for øyeblikket to typer klynger som er tilgjengelige – husholdning og tilpassede klynger. Systemet velger automatisk en husholdning med forhåndsdefinerte regler hvis *Kunde*-enheten inneholder de semantiske felter *Person.LastName* og *Location.Address*. Du kan også opprette en klynge med dine egne regler og betingelser, omtrent som [samsvarsregler](match-entities.md#define-rules-for-match-pairs).

1. Velg **Avansert** > **Opprett klynge**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontroll for å opprette en ny klynge.":::

1. Velg mellom en **Husholdning** eller en **Egendefinert**. Hvis de semantiske feltene *Person.LastName* og *Location.Address* finnes i *Kunde*-enheten, velges husholdning automatisk.

1. Angi et navn for klyngen, og velg **Fullført**.

1. Velg kategorien **Klynger** for å finne klyngen du opprettet.

1. Angi reglene og betingelsene for å definere klyngen.

1. Velg **Ferdig**. Klyngen opprettes når samlingsprosessen er fullført. Klyngeidentifikatorene legges til som nye felt i *Kunde*-enheten.

> [!div class="nextstepaction"]
> [Neste trinn: Se gjennom samlingen](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
