---
title: Slå sammen enheter i dataforening
description: Slå sammen enheter for å opprette enhetlige kundeprofiler.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 24b523786158ff36c314601846ee25ea64cfabbe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650238"
---
# <a name="merge-entities"></a>Slå sammen enheter

Sammenslåingsfasen er den siste fasen i datasamlingsprosessen. Formålet er avstemming av data er i konflikt. Eksempler på motstridende data kan omfatte et kundenavn som finnes i to av datasettene, men som vises litt ulikt i hvert sett ("Kari Nordmann" kontra "Kari Nordman"), eller et telefonnummer som er forskjellig i format (617-803-091X kontra 617803091X). Sammenslåing av de motstridende datapunktene utføres på attributtbasis.

:::image type="content" source="media/merge-fields-page.png" alt-text="Slå sammen-siden i dataforeningsprosessen som viser tabell med sammenslåtte felter som definerer den enhetlige kundeprofilen.":::

Når du har fullført [samsvarsfasen](match-entities.md), kan du starte sammenslåingsfasen ved å velge flisen **Flett** på siden **Samle**.

## <a name="review-system-recommendations"></a>Gå gjennom systemanbefalinger

I **Data** > **Samle** > **Slå sammen** velger og utelater du attributter som skal slås sammen inn i enheten for enhetlig kundeprofil. Den enhetlige kundeprofilen er et resultat av dataforeningsprosessen. Noen attributter blir automatisk slått sammen av systemet.

Hvis du vil vise attributtene som er inkludert i ett av de automatisk sammenslåtte attributtene, velger du det sammenslåtte attributtet i fanen **Kundefelter** i tabellen. Attributtene som utgjør det sammenslåtte attributtet, vises i to nye rader under det flettede attributtet.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Del opp, gi nytt navn til, utelat og rediger sammenslåtte felter

Du kan endre hvordan systemet behandler sammenslåtte attributter for å generere den enhetlige kundeprofilen. Velg **Vis mer** og velg hva du vil endre.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Alternativer i rullegardinmenyen Vis mer for å behandle sammenslåtte attributter.":::

Se følgende deler hvis du vil ha mer informasjon.

## <a name="separate-merged-fields"></a>Del sammenslåtte felter

Du skiller sammenslåtte felter ved å finne attributtet i tabellen. Delte felter vises som individuelle datapunkter i den enhetlige kundeprofilen. 

1. Velg det sammenslåtte feltet.
  
1. Velg **Vis mer** og velg **Del felter**.
 
1. Bekreft delingen.

1. Velg **Lagre** og **Kjør** for å behandle endringene.

## <a name="rename-merged-fields"></a>Gi nytt navn til sammenslåtte felter

Endre visningsnavnet for sammenslåtte attributter. Du kan ikke endre navnet på utdataenheten.

1. Velg det sammenslåtte feltet.
  
1. Velg **Vis mer** og velg **Gi nytt navn**.

1. Bekreft det endrede visningsnavnet. 

1. Velg **Lagre** og **Kjør** for å behandle endringene.

## <a name="exclude-merged-fields"></a>Utelatt sammenslåtte felter

Utelat et attributt fra den enhetlige kundeprofilen. Hvis feltet brukes i andre prosesser, for eksempel i et segment, fjerner du det fra disse prosessene før du utelater det fra kundeprofilen. 

1. Velg det sammenslåtte feltet.
  
1. Velg **Vis mer** og velg **Utelat**.

1. Bekreft utelatelsen.

1. Velg **Lagre** og **Kjør** for å behandle endringene. 

Velg **Utelatte felter** på **Slå sammen**-siden for å vise listen over alle utelatte felter. I denne ruten kan du legge til utelatte felter på nytt.

## <a name="manually-combine-fields"></a>Kombiner felter manuelt

Angi et sammenslått attributt manuelt. 

1. Velg **Kombiner felter** på **Slå sammen**-siden.

1. Angi et **navn** og et **navn på utdatafelt**.

1. Veg et felt du vil legge til. Velg **Legg til felter** for å kombinere flere felter.

1. Bekreft utelatelsen.

1. Velg **Lagre** og **Kjør** for å behandle endringene. 

## <a name="change-the-order-of-fields"></a>Endre rekkefølgen på feltene

Noen enheter inneholder flere detaljer enn andre. Hvis en enhet inneholder de nyeste dataene om et felt, kan du prioritere det over andre enheter ved å slå sammen verdier.

1. Velg det sammenslåtte feltet.
  
1. Velg **Vis mer** og velg **Rediger**.

1. Velg **Flytt opp/ned** i **Kombiner felter**-ruten for å angi rekkefølgen, eller dra og slipp dem i ønsket posisjon.

1. Bekreft endringen.

1. Velg **Lagre** og **Kjør** for å behandle endringene.

## <a name="run-your-merge"></a>Kjøre flettingen

Uansett om du slår sammen attributter manuelt eller lar programmet slå dem sammen, kan du alltid kjøre flettingen. Velg **Kjør** på siden **Slå sammen** for å starte prosessen.

> [!div class="mx-imgBorder"]
> ![Lagre og kjøre datasammenslåing.](media/configure-data-merge-save-run.png "Lagre og kjøre datasammenslåing")

Velg **Kjør bare fletting** hvis du bare vil vise utdataene i enheten for enhetlig kunde. Nedstrømsprosesser oppdateres som [definert i oppdateringsplanen](system.md#schedule-tab).

Velg **Kjør fletting og nedstrømsprosesser** for å oppdatere systemet med endringene. Alle prosesser, inkludert supplering, segmenter og mål, kjører på nytt automatisk. Når alle nedstrømsprosesser er fullført, gjenspeiler kundeprofilene endringene du har gjort.

Hvis du vil gjøre flere endringer og kjøre trinnet på nytt, kan du avbryte en pågående fletting. Velg **Oppdaterer ...**, og velg **Avbryt jobb** i sideruten som vises.

> [!TIP]
> Når du har kjørt sammenslåingsprosessen, velger du prosessstatusen for å åpne ruten **Oppgavedetaljer**. Den gir en oversikt over behandlingstiden, den siste behandlingsdatoen og alle feil og advarsler som er knyttet til oppgaven. Velg **Se detaljer** for å se hvilke enheter som deltok i samsvarsprosessen, om konfliktoppløsningen er vellykket, og om oppdateringene ble publisert på riktig måte.  
> Det finnes [seks typer statuser](system.md#status-types) for oppgaver/prosesser. De fleste prosesser er i tillegg [avhengig av andre nedsstrømsprosesser](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Neddrillingsbane for å komme til å behandle detaljer fra aktivitetsstatuskoblingen.":::

## <a name="next-step"></a>Neste trinn

Konfigurer [aktiviteter](activities.md), [supplering](enrichment-hub.md) eller [relasjoner](relationships.md) for å få mer informasjon om kundene.

Hvis du allerede har konfigurert aktiviteter, supplering eller segmenter, behandles de automatisk for å bruke de nyeste kundedataene.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
