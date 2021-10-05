---
title: Relasjoner mellom enheter og enhetsbaner
description: Opprett og administrer relasjoner mellom enheter fra flere datakilder.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c639cfca30cf1b57ada7d728311210b7210a37ac
ms.sourcegitcommit: f72d5b86dfdc7282c6c1918b1ab3962d7a1c9852
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/27/2021
ms.locfileid: "7557364"
---
# <a name="relationships-between-entities"></a>Relasjoner mellom enheter

Relasjoner kobler sammen enheter og definerer en graf for dataene når enheter deler en felles identifikator, en sekundærnøkkel. Denne sekundærnøkkelen kan referere fra én enhet til en annen. Tilkoblede enheter gjør at segmenter og mål kan defineres basert på flere datakilder.

Det finnes tre typer relasjoner: 
- systemrelasjoner som ikke kan redigeres, og som opprettes av systemet som en del av dataforeningsprosessen
- arvede relasjoner som ikke kan redigeres, og som opprettes automatisk fra inntak av datakilder 
- egendefinerte relasjoner som kan redigeres, og som opprettes og konfigureres av brukere

## <a name="non-editable-system-relationships"></a>Systemrelasjoner som ikke kan redigeres

Under dataforening opprettes systemrelasjoner automatisk basert på intelligent samsvar. Disse relasjonene hjelper deg å knytte kundeprofiloppføringene til tilsvarende oppføringer. Diagrammet nedenfor illustrerer opprettelsen av tre systembaserte relasjoner. Kundeenheten sammenlignes med andre enheter for å produsere den enhetlige *Kunde*-enheten.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram med relasjonsbaner for kundeenheten med tre 1:N-relasjoner.":::

- ***CustomerToContact*-relasjon** ble opprettet mellom *Kunde*-enheten og *Kontakt*-enheten. *Kunde*-enheten får nøkkelfeltet **Contact_contactID** til å knyttes til nøkkelfeltet **contactID** for *Kontakt*-enheten.
- ***CustomerToAccount*-relasjon** ble opprettet mellom *Kunde*-enheten og *Konto*-enheten. *Kunde*-enheten får nøkkelfeltet **Account_accountID** til å knyttes til nøkkelfeltet **accountID** for *Konto*-enheten.
- ***CustomerToWebAccount*-relasjon** ble opprettet mellom *Kunde*-enheten og *WebAccount*-enheten. *Kunde*-enheten får nøkkelfeltet **WebAccount_webaccountID** til å knyttes til nøkkelfeltet **webaccountID** for *WebAccount*-enheten.

## <a name="non-editable-inherited-relationships"></a>Arvede relasjoner som ikke kan redigeres

Under datainntaksprosessen kontrollerer systemet datakilder for eksisterende relasjoner. Hvis ingen relasjoner finnes, oppretter systemet dem automatisk. Disse relasjonene brukes også i nedstrømsprosesser.

## <a name="create-a-custom-relationship"></a>Opprette en egendefinert relasjon

Relasjonen består av en *kildeenhet* som inneholder sekundærnøkkelen og en *målenhet* som kildeenhetens sekundærnøkkel peker mot. 

1. I Målgruppeinnsikt går du til **Data** > **Relasjoner**.

2. Velg **Ny relasjon**.

3. Angi følgende informasjon i ruten **Ny relasjon**:

   :::image type="content" source="media/relationship-add.png" alt-text="Sideruten Ny relasjon med tomme inndatafelter.":::

   - **Relasjonsnavn**: Navn som gjenspeiler formålet med relasjonen. Eksempel: CustomerToSupportCase.
   - **Beskrivelse**: Beskrivelse av relasjonen.
   - **Kildeenhet**: Enhet som brukes som en kilde i relasjonen. Eksempel: SupportCase.
   - **Målenhet**: Enhet som brukes som et mål i relasjonen. Eksempel: Kunde.
   - **Kildekardinalitet**: Angi kardinaliteten til kildeenheten. Kardinalitet beskriver antall mulige elementer i et sett. Den er alltid relatert til målkardinaliteten. Du kan velge mellom **Én** og **Mange**. Bare mange-til-én- og én-til-én-relasjoner støttes.  
     - Mange-til-én: Flere kildeoppføringer kan knyttes til én måloppføring. Eksempel: Flere kundestøttesaker fra én kunde.
     - Én-til-én: Én kildeoppføring er knyttet til én måloppføring. Eksempel: Én fordels-ID for én kunde.

     > [!NOTE]
     > Mange-til-mange-relasjoner kan opprettes ved hjelp av to mange-til-én-relasjoner og en koblingsenhet, som kobler sammen kildeenheten og målenheten.

   - **Målkardinalitet**: Velg kardinaliteten for målenhetsoppføringene. 
   - **Kildenøkkelfelt**: Sekundærnøkkelfeltet i kildeenheten. Eksempel: SupportCase kan bruke CaseID som et sekundærnøkkelfelt.
   - **Målprogramfelt**: Nøkkelfeltet for målenheten. Eksempel: Kunde kan bruke nøkkelfeltet **CustomerID**.

4. Velg **Lagre** for å opprette den egendefinerte relasjonen.

## <a name="view-relationships"></a>Vise relasjoner

Relasjoner-siden viser alle relasjonene som er opprettet. Hver rad representerer en relasjon, som også omfatter detaljer om kildeenheten, målenheten og kardinaliteten. 

:::image type="content" source="media/relationships-list.png" alt-text="Liste over relasjoner og alternativer på handlingslinjen på Relasjoner-siden.":::

Denne siden har et sett med alternativer for eksisterende og nye relasjoner: 
- **Ny relasjon**: [Opprett en egendefinert relasjon](#create-a-custom-relationship).
- **Visualisering**: [Utforsk relasjonsvisualiseringen](#explore-the-relationship-visualizer) for å se et nettverksdiagram over eksisterende relasjoner og kardinaliteten deres.
- **Filtrer etter**: Velg hvilken type relasjoner som skal vises i listen.
- **Søk etter relasjoner**: Bruk et tekstbasert søk etter egenskaper i relasjoner.

### <a name="explore-the-relationship-visualizer"></a>Utforske relasjonsvisualiseringen

Relasjonsvisualiseringen viser et nettverksdiagram over eksisterende relasjoner mellom tilkoblede enheter og kardinaliteten deres. Den visualiserer også relasjonsbanen.

Hvis du vil tilpasse visningen, kan du endre plasseringen til boksene ved å dra dem på lerretet.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Skjermbilde av nettverksdiagrammet for relasjonsvisualisering med tilkoblinger mellom relaterte enheter.":::

Tilgjengelige alternativer: 
- **Eksporter som bilde**: Lagre gjeldende visning som en bildefil.
- **Endre til vannrett/loddrett oppsett**: Endre justeringen av enhetene og relasjonene.
- **Rediger**: Oppdater egenskaper for egendefinerte relasjoner i redigeringsruten, og lagre endringer.

## <a name="relationship-paths"></a>Relasjonsbaner

En relasjonsbane beskriver enhetene som er koblet til relasjoner en kildeenhet og en målenhet. Den brukes når du oppretter et segment eller et mål som inkluderer andre enheter enn enheten for enhetlig profil, og når det finnes flere alternativer for å nå enheten for enhetlig profil. 

En relasjonsbane informerer systemet om relasjoner for å få tilgang til enheten for den enhetlige profilen. Forskjellige relasjonsbaner kan gi forskjellige resultater.

Enheten *eCommerce_eCommercePurchases* har for eksempel følgende relasjoner for enheten for den enhetlige profilen *Kunde*:

- eCommerce_eCommercePurchases > Kunde
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Kunde
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Kunde 

En relasjonsbane avgjør hvilke enheter du kan bruke når du oppretter regler for målinger eller segmenter. Valg av alternativet med den lengste relasjonsbanen vil sannsynligvis gi færre resultater fordi de samsvarende oppføringene må være en del av alle enheter. I dette eksemplet må en kunde ha kjøpt varer via e-handel(eCommerce_eCommercePurchases), på et salgssted (POS_posPurchases) og delta i fordelsprogrammet (loyaltyScheme_loyCustomers). Når du velger det første alternativet, får du sannsynligvis flere resultater fordi kunder bare trenger å eksistere i én tilleggsenhet.

### <a name="direct-relationship"></a>Direkte relasjon

En relasjon klassifiseres som en **direkte relasjon** når en kildeenhet er relatert til en målenhet med bare én relasjon.

Hvis for eksempel en aktivitetsenhet med navnet *eCommerce_eCommercePurchases* kobles til en målenhet *eCommerce_eCommerceContacts* bare via *ContactId*, er det en direkte relasjon.

:::image type="content" source="media/direct_Relationship.png" alt-text="Kildeenhet kobler direkte til målenheten.":::

#### <a name="multi-path-relationship"></a>Relasjon med flere baner

En **relasjon med flere baner** er en spesiell type direkte relasjon som kobler en kildeenhet til mer enn én målenhet.

Hvis for eksempel en aktivitetsenhet med navnet *eCommerce_eCommercePurchases* er relatert til to målenheter, er både *eCommerce_eCommerceContacts* og *loyaltyScheme_loyCustomers* en relasjon med flere baner.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Kildeenhet kobler direkte til mer enn én målenhet via en relasjon med flere mellomstasjoner.":::

### <a name="indirect-relationship"></a>Indirekte relasjon

En relasjon klassifiseres som en **indirekte relasjon** når en kildeenhet er relatert til en eller flere enheter før den relateres til en relasjon.

#### <a name="multi-hop-relationship"></a>Relasjon med flere mellomstasjoner

En *relasjon med flere mellomstasjoner* er en indirekte relasjon som gjør det mulig å koble en kildeenhet til en målenhet via en eller flere andre *mellomenheter*.

Hvis for eksempel en aktivitetsenhet som heter *eCommerce_eCommercePurchasesWest* kobler til en midlertidig enhet kalt *eCommerce_eCommercePurchasesEast* og deretter kobler til en målenhet som heter *eCommerce_eCommerceContacts*, er det en relasjon med flere mellomstasjoner.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Kildeenhet kobler direkte til en målenhet med en midlertidig enhet.":::

### <a name="multi-hop-multi-path-relationship"></a>Relasjon med flere baner og flere mellomstasjoner

Relasjoner for flere mellomstasjoner og flere baner kan brukes sammen til å opprette **flere mellomstasjoner, flere baner**. Denne spesialtypen kombinerer funksjonene for **flere mellomstasjoner** og **relasjoner med flere baner**. Den lar deg koble til mer enn én målenhet når du bruker mellomliggende enheter.

Hvis for eksempel en aktivitetsenhet som heter *eCommerce_eCommercePurchasesWest* kobler til en midlertidig enhet kalt *eCommerce_eCommercePurchasesEast* og deretter kobler til to målenheter, både *eCommerce_eCommerceContacts* og *loyaltyScheme_loyCustomers*, er det en relasjon med flere mellomstasjoner og flere baner.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Kildeenhet kobler direkte til én målenhet og kobler til en annen målenhet via en mellomliggende enhet.":::

## <a name="manage-existing-relationships"></a>Administrere eksisterende relasjoner 

Hver relasjon representeres av en rad på Relasjoner-siden. 

Velg en relasjon, og velg ett av følgende alternativer: 
 
- **Rediger**: Oppdater egenskaper for egendefinerte relasjoner i redigeringsruten, og lagre endringer.
- **Slett**: Slett egendefinerte relasjoner.
- **Vis**: Vis systemopprettede og arvede relasjoner. 

## <a name="next-step"></a>Neste trinn

Systemrelasjoner og egendefinerte relasjoner brukes til å [opprette segmenter](segments.md) og [målinger](measures.md) basert på flere datakilder som ikke lenger finnes i siloer.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
