---
title: Slå sammen enheter i dataforening
description: Slå sammen enheter for å opprette enhetlige kundeprofiler.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896523"
---
# <a name="merge-entities"></a>Slå sammen enheter

Sammenslåingsfasen er den siste fasen i datasamlingsprosessen. Formålet er avstemming av data er i konflikt. Eksempler på motstridende data kan omfatte et kundenavn som finnes i to av datasettene, men som vises litt ulikt i hvert sett ("Kari Nordmann" kontra "Kari Nordman"), eller et telefonnummer som er forskjellig i format (617-803-091X kontra 617803091X). Sammenslåing av de motstridende datapunktene utføres på attributtbasis.

Når du har fullført [samsvarsfasen](match-entities.md), kan du starte sammenslåingsfasen ved å velge flisen **Flett** på siden **Samle**.

## <a name="review-system-recommendations"></a>Gå gjennom systemanbefalinger

På siden **Flett** velger og utelater du attributter som skal slås sammen i den enhetlige kundeprofilenheten (resultatet av konfigurasjonsprosessen). Noen attributter blir automatisk slått sammen av systemet.

### <a name="view-merged-attributes"></a>Vise sammenslåtte attributter

Hvis du vil vise attributtene som er inkludert i et av de automatisk sammenslåtte attributtene, velger du det sammenslåtte attributtet. De to attributtene som utgjør det flettede attributtet, vises i to nye rader under det flettede attributtet.

> [!div class="mx-imgBorder"]
> ![Velg sammenslått attributt](media/configure-data-merge-profile-attributes.png "Velge sammenslått attributt")

### <a name="separate-merged-attributes"></a>Separat sammenslåtte attributter

Hvis du vil skille eller fjerne sammenslåingen av noen av de automatisk flettede attributtene, kan du finne attributtet i tabellen **Profilattributter**.

1. Merk elliseknappen (...).
  
2. Velg **Separate felt** i rullegardinlisten.

### <a name="remove-merged-attributes"></a>Fjerne sammenslåtte attributter

Hvis du vil utelate et attributt fra den endelige kundeprofilenheten, finner du det i tabellen **Profilattributter**.

1. Merk elliseknappen (...).
  
2. Velg **Ikke slå sammen** i rullegardinlisten.

   Attributtet flyttes til delen **Fjernet fra kundeoppføring**.

## <a name="manually-add-a-merged-attribute"></a>Legge til et flettet attributt manuelt

Hvis du vil legge til et flettet attributt, går du til siden **Slå sammen**.

1. Velg **Legg til sammenslått attributt**.

2. Angi et **Navn** for å identifisere det på siden **Slå sammen** senere.

3. Du kan eventuelt angi et **Visningsnavn** som skal vises i den enhetlige kundeprofilenheten.

4. Konfigurer **Velg duplikatattributter** for å velge attributtene du vil slå sammen, fra de samsvarende enhetene. Du kan også søke etter attributter.

5. Angi **Ranger etter viktighet** for å prioritere ett attributt over de andre. Hvis for eksempel enheten *WebAccountCSV* inneholder de mest nøyaktige dataene om attributtet *Fullt navn*, kan du prioritere denne enheten over *ContactCSV* ved å velge *WebAccountCSV*. Som et resultat flytter *WebAccountCSV* til førsteprioritet, mens *ContactCSV* flytter til andreprioritet når det hentes verdier for attributet *Fullt navn*.

## <a name="run-your-merge"></a>Kjøre flettingen

Uansett om du slår sammen attributter manuelt eller lar programmet slå dem sammen, kan du alltid kjøre flettingen. Velg **Kjør** på siden **Slå sammen** for å starte prosessen.

> [!div class="mx-imgBorder"]
> ![Lagre og kjøre datasammenslåing](media/configure-data-merge-save-run.png "Lagre og kjøre datasammenslåing")

Hvis du vil gjøre flere endringer og kjøre trinnet på nytt, kan du annullere en sammenslåing som pågår. Velg **Oppdaterer ...**, og velg **Avbryt jobb** i sideruten som vises.

Etter at teksten **Oppdaterer ...** endres til **Vellykket**, har sammenslåingen fullført og løst motstridende data i henhold til policyene du definerte. Sammenslåtte og ikke-sammenslåtte attributter er inkludert i den enhetlige profilenheten. Utelukkede attributter er ikke inkludert i den enhetlige profilenheten.

Hvis det ikke var første gang du kjørte en sammenslåing, vil alle nedstrømsprosesser, inkludert supplering, segmentering og tiltak, kjøres på nytt automatisk. Når alle nedstrømsprosessene er kjørt på nytt, gjenspeiler kundeprofilene eventuelle endringer du har gjort.

> [!TIP]
> Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser. De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies). Du kan velge statusen for en prosess for å vise detaljer om fremdriften for hele jobben. Etter at du har valgt **Vis detaljer** for en av jobbenes oppgaver, finner du tilleggsinformasjon: behandlingstid, dato for siste behandling og alle feil og advarsler som er knyttet til oppgaven.

## <a name="next-step"></a>Neste trinn

Konfigurer [aktiviteter](activities.md), [supplering](enrichment-hub.md) eller [relasjoner](relationships.md) for å få mer informasjon om kundene.

Hvis du allerede har konfigurert aktiviteter, suppleringer eller relasjoner, eller hvis du definerte segmenter, blir de automatisk behandlet for å bruke de nyeste kundedataene.




[!INCLUDE[footer-include](../includes/footer-banner.md)]