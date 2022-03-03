---
title: Slå sammen enheter i dataforening
description: Slå sammen enheter for å opprette enhetlige kundeprofiler.
ms.date: 01/28/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: c7743104bf89d9a2a741f1b358a89ed0240be024
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355857"
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

1. Velg et flettet felt.
  
1. Velg **Vis mer** og velg **Utelat**.

1. Bekreft utelatelsen.

1. Velg **Lagre** og **Kjør** for å behandle endringene. 

Velg **Utelatte felter** på **Slå sammen**-siden for å vise listen over alle utelatte felter. I denne ruten kan du legge til utelatte felter på nytt.

## <a name="edit-a-merged-field"></a>Rediger et sammenslått felt

1.  Velg et flettet felt.

1.  Velg **Vis mer** og velg **Rediger**.

1.  Angi hvordan du vil kombinere eller flette feltene fra et av tre alternativer:
    - **Viktighet**: Identifiserer vinnerverdien basert på viktighetsrangering angitt for de deltagende feltene. Dette er standardalternativet for sammenslåing. Velg **Flytt opp/ned** for å angi viktighetsrangering.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Viktighetsalternativ i dialogboksen for flettefelter."::: 
    - **Nyeste**: Identifiserer vinnerverdien basert på mest nylige. Krever en dato eller et numerisk felt for hver enhet som deltar i omfanget for flettefeltene, for å definere nyligheten.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Nylighetsalternativ i dialogboksen for flettefelter.":::
    - **Minst nylig**: Identifiserer vinnerverdien basert på minste nylighet. Krever en dato eller et numerisk felt for hver enhet som deltar i omfanget for flettefeltene, for å definere nyligheten.

1.  Du kan legge til flere felt for å delta i fletteprosessen.

1.  Du kan gi nytt navn til det flettede feltet.

1. Velg **Ferdig** for å ta i bruk endringene.

1. Velg **Lagre** og **Kjør** for å behandle endringene. 

## <a name="combine-fields-manually"></a>Slå sammen felter manuelt

Angi et sammenslått attributt manuelt.

1. Velg **Kombiner** på **Slå sammen**-siden.

1. Velg **Felter**-alternativet.

1. Angi vinnerregelen for sammenslåing i **Kombiner felter etter** rullegardinmenyen.

1. Veg et felt du vil legge til. Velg **Legg til felter** for å kombinere flere felter.

1. Angi et **navn** og et **navn på utdatafelt**.

1. Velg **Ferdig** for å ta i bruk endringene.

1. Velg **Lagre** og **Kjør** for å behandle endringene. 

## <a name="combine-a-group-of-fields"></a>Slå sammen en gruppe felter

Behandle en gruppe felter som én enkelt enhet. Hvis oppføringene for eksempel inneholder feltene Adresse1, Adresse2, Poststed og Postnummer. Vi vil sannsynligvis ikke slå sammen Adresse2 for en annen oppføring, da det kan tenkes at det vil gjøre dataene mer fullstendige

1. Velg **Kombiner** på **Slå sammen**-siden.

1. Velg **Gruppe felter**-alternativet.

1. Angi vinnerregelen for sammenslåing i **Ranger grupper etter**-rullegardinlisten.

1. Velg **Legg til**, og velg om du vil legge til flere felter eller tilleggsgrupper i feltene.

1. Angi et **navn** og et **utdatanavn** for hvert kombinerte felt.

1. Oppgi et **navn** for gruppen felter. 

1. Velg **Ferdig** for å ta i bruk endringene.

1. Velg **Lagre** og **Kjør** for å behandle endringene.

## <a name="change-the-order-of-fields"></a>Endre rekkefølgen på feltene

Noen enheter inneholder flere detaljer enn andre. Hvis en enhet inneholder de nyeste dataene om et felt, kan du prioritere det over andre enheter ved å slå sammen verdier.

1. Velg det sammenslåtte feltet.
  
1. Velg **Vis mer** og velg **Rediger**.

1. Velg **Flytt opp/ned** i **Kombiner felter**-ruten for å angi rekkefølgen, eller dra og slipp dem i ønsket posisjon.

1. Bekreft endringen.

1. Velg **Lagre** og **Kjør** for å behandle endringene.

## <a name="configure-customer-id-generation"></a>Konfigurer kunde-ID-generering 

Når du har konfigurert sammenslåingsfelter, kan du definere hvordan du vil generere CustomerId-verdier, de unike kundeprofilidentifikatorene. Flettetrinnet i datasammenslåingsprosessen genererer den unike kundeprofilidentifikatoren. Identifikatoren er CustomerId i *Kunde*-enheten som er et resultat av dataenhetsprosessen. 

CustomerId i kundeenheten er basert på et nummer for den første verdien til primærnøklene som ikke er nullvinner. Disse nøklene kommer fra enhetene som brukes i samsvars- og sammenslåingsfasen, og påvirkes av samsvarsrekkefølgen. Den genererte CustomerID kan derfor endres når en primærnøkkelverdi endres i primærenheten i samsvarsordren. Primærnøkkelverdien representerer kanskje ikke alltid samme kunde.

Konfigurasjon av en stabil kunde-ID gjør det mulig å unngå denne virkemåten.

**Konfigurer en unik kunde-ID**

1. Gå til **Samle** > **Slå sammen**.

1. Velg kategorien **Nøkler**. 

1. Hold markøren over **CustomerId**-raden, og velg alternativet **Konfigurer**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontroller for å tilpasse ID-genereringen.":::

1. Velg opptil fem felter som vil bestå av en unik kunde-ID og er mer stabil. Oppføringer som ikke samsvarer med konfigurasjonen, bruker i stedet en systemkonfigurert ID.  

1. Velg **Fullført**, og kjør fletteprosessen for å ta i bruk endringene.

## <a name="group-profiles-into-households-or-clusters"></a>Grupper profiler i husholdninger eller klynger

Som en del av konfigurasjonsprosessen for kundeprofilgenerering kan du definere regler for å gruppere relaterte profiler i en klynge. Det finnes for øyeblikket to typer klynger som er tilgjengelige – husholdning og tilpassede klynger. Systemet velger automatisk en husholdning med forhåndsdefinerte regler hvis *Kunde*-enheten inneholder de semantiske felter *Person.LastName* og *Location.Address*. Du kan også opprette en klynge med dine egne regler og betingelser, omtrent som [samsvarsregler](match-entities.md#define-rules-for-match-pairs).

**Definere en husholdning eller en klynge**

1. Gå til **Samle** > **Slå sammen**.

1. Velg **Avansert** > **Opprett klynge** i kategorien **Opprett klynge**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontroll for å opprette en ny klynge.":::

1. Velg mellom en **Husholdning** eller en **Egendefinert**. Hvis de semantiske feltene *Person.LastName* og *Location.Address* finnes i *Kunde*-enheten, velges husholdning automatisk.

1. Angi et navn for klyngen, og velg **Fullført**.

1. Velg kategorien **Klynger** for å finne klyngen du opprettet.

1. Angi reglene og betingelsene for å definere klyngen.

1. Velg **Kjør** for å kjøre fletteprosessen og opprette klyngen.

Når du har kjørt sammenslåingsprosessen, legges klyngeidentifikatorene til som nye felt i *Kunde*-enheten.

## <a name="run-your-merge"></a>Kjøre flettingen

Uansett om du slår sammen attributter manuelt eller lar programmet slå dem sammen, kan du alltid kjøre flettingen. Velg **Kjør** på siden **Slå sammen** for å starte prosessen.

> [!div class="mx-imgBorder"]
> ![Lagre og kjøre datasammenslåing.](media/configure-data-merge-save-run.png "Lagre og kjøre datasammenslåing")

Velg **Kjør bare fletting** hvis du bare vil vise utdataene i enheten for enhetlig kunde. Nedstrømsprosesser oppdateres som [definert i oppdateringsplanen](system.md#schedule-tab).

Velg **Kjør fletting og nedstrømsprosesser** for å oppdatere systemet med endringene. Alle prosesser, inkludert supplering, segmenter og mål, kjører på nytt automatisk. Når alle nedstrømsprosesser er fullført, gjenspeiler kundeprofilene endringene du har gjort.

Hvis du vil gjøre flere endringer og kjøre trinnet på nytt, kan du avbryte en pågående fletting. Velg **Oppdaterer ...**, og velg **Avbryt jobb** i sideruten som vises.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Neddrillingsbane for å komme til å behandle detaljer fra aktivitetsstatuskoblingen.":::

## <a name="next-step"></a>Neste trinn

Konfigurer [aktiviteter](activities.md), [supplering](enrichment-hub.md) eller [relasjoner](relationships.md) for å få mer informasjon om kundene.

Hvis du allerede har konfigurert aktiviteter, supplering eller segmenter, behandles de automatisk for å bruke de nyeste kundedataene.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
