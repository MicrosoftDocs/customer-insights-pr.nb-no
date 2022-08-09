---
title: Relasjoner mellom enheter og enhetsbaner
description: Opprett og administrer relasjoner mellom enheter fra flere datakilder.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183580"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Relasjoner mellom enheter og enhetsbaner

Relasjoner kobler sammen enheter og definerer en graf for dataene når enheter deler en felles identifikator, en sekundærnøkkel. Denne sekundærnøkkelen kan referere fra én enhet til en annen. Tilkoblede enheter gjør at segmenter og mål kan defineres basert på flere datakilder.

Det finnes tre typer relasjoner: 
- Systemrelasjoner som ikke kan redigeres, opprettes av systemet som en del av dataforeningsprosessen
- Arvede relasjoner som ikke kan redigeres, opprettes automatisk fra inntak av datakilder
- Egendefinerte relasjoner som kan redigeres, opprettes og konfigureres av brukere

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

1. Gå til **Data** > **Relasjoner**.

2. Velg **Ny relasjon**.

3. Angi følgende informasjon i ruten **Ny relasjon**:

   :::image type="content" source="media/relationship-add.png" alt-text="Sideruten Ny relasjon med tomme inndatafelter.":::

   - **Relasjonsnavn**: Navn som gjenspeiler formålet med relasjonen. Eksempel: CustomerToSupportCase.
   - **Beskrivelse**: Beskrivelse av relasjonen.
   - **Kildeenhet**: Enhet som brukes som en kilde i relasjonen. Eksempel: SupportCase.
   - **Målenhet**: Enhet som brukes som et mål i relasjonen. Eksempel: Kunde.
   - **Kildekardinalitet**: kardinaliteten til kildeenheten. Kardinalitet beskriver antall mulige elementer i et sett. Den er alltid relatert til målkardinaliteten. Du kan velge mellom **Én** og **Mange**. Bare mange-til-én- og én-til-én-relasjoner støttes.  
     - Mange-til-én: Flere kildeoppføringer kan knyttes til én måloppføring. Eksempel: Flere kundestøttesaker fra én kunde.
     - Én-til-én: Én kildeoppføring er knyttet til én måloppføring. Eksempel: Én fordels-ID for én kunde.

     > [!NOTE]
     > Mange-til-mange-relasjoner kan opprettes ved hjelp av to mange-til-én-relasjoner og en koblingsenhet, som kobler sammen kildeenheten og målenheten.

   - **Målkardinalitet**: kardinaliteten til målenhetsoppføringene.
   - **Kildenøkkelfelt**: sekundærnøkkelfeltet i kildeenheten. Eksempel: SupportCase bruker **CaseID** som sekundærnøkkelfelt.
   - **Målnøkkelfelt**: nøkkelfeltet for målenheten. Eksempel: Kunde bruker **CustomerID** som nøkkelfelt.

4. Velg **Lagre** for å opprette den egendefinerte relasjonen.

## <a name="set-up-account-hierarchies"></a>Opprette kontohierarkier

Miljøer som er konfigurert slik at de bruker forretningsforbindelser som primær målgruppe, kan konfigurere forretningsforbindelseshierarkier for relaterte forretningsforbindelser. For eksempel et selskap som har separate forretningsenheter.

Organisasjoner oppretter forretningsforbindelseshierarkier for bedre å administrere forretningsforbindelser og relasjoner med hverandre. Customer Insights støtter overordnede-underordnede-forretningsforbindelseshierarkier som allerede finnes i innsatte kundedata. For eksempel forretningsforbindelser fra Dynamics 365 Sales. Disse hierarkiene kan konfigureres på **Relasjoner**-siden.

1. Gå til **Data** > **Relasjoner**.
1. Velg kategorien **Kontohierarki**.
1. Velg **Nytt hierarki for forretningsforbindelse**.
1. Angi et navn på hierarkiet i ruten **Kontohierarki**. Systemet oppretter et navn for utdataenheten, men du kan endre det.
1. Velg enheten som inneholder kontohierarkiet. Det er vanligvis i samme enhet som inneholder forretningsforbindelsene.
1. Velg **Forretningsforbindelses-UID** og **Overordnet UID** fra den valgte enheten.
1. Velg **Lagre** for å fullføre forretningsforbindelseshierarkiet.

## <a name="manage-existing-relationships"></a>Administrere eksisterende relasjoner

Gå til **Relasjoner**-siden for å vise alle relasjonene som er opprettet, samt kildeenheten, målenheten og kardinaliteten deres.

:::image type="content" source="media/relationships-list.png" alt-text="Liste over relasjoner og alternativer på handlingslinjen på Relasjoner-siden.":::

Bruk alternativene **Filtrer etter** eller **Relasjoner** til å finne en bestemt relasjon. Hvis du vil se et nettverksdiagram over eksisterende relasjoner og kardinaliteten deres, velger du [**Visualisering**](#explore-the-relationship-visualizer).

Velg en relasjon for å vise tilgjengelige handlinger:
- **Rediger**: Oppdater egenskaper for egendefinerte relasjoner i redigeringsruten, og lagre endringer.
- **Slett**: Slett egendefinerte relasjoner.
- **Vis**: Vis systemopprettede og arvede relasjoner.

### <a name="explore-the-relationship-visualizer"></a>Utforske relasjonsvisualiseringen

Relasjonsvisualiseringen viser et nettverksdiagram over eksisterende relasjoner mellom tilkoblede enheter og kardinaliteten deres. Den visualiserer også relasjonsbanen.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Skjermbilde av nettverksdiagrammet for relasjonsvisualisering med tilkoblinger mellom relaterte enheter.":::

Hvis du vil tilpasse visningen, kan du endre plasseringen til boksene ved å dra dem på lerretet. Andre alternativer omfatter følgende: 
- **Eksporter som bilde**: Lagre gjeldende visning som en bildefil.
- **Endre til vannrett/loddrett oppsett**: Endre justeringen av enhetene og relasjonene.
- **Rediger**: Oppdater egenskaper for egendefinerte relasjoner i redigeringsruten, og lagre endringer.

## <a name="relationship-paths"></a>Relasjonsbaner

En relasjonsbane beskriver enhetene som er koblet til relasjoner en kildeenhet og en målenhet. Den brukes når du oppretter et segment eller et mål som inkluderer andre enheter enn enheten for enhetlig profil, og når det finnes flere alternativer for å nå enheten for enhetlig profil. Forskjellige relasjonsbaner kan gi forskjellige resultater.

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

En **relasjon med flere mellomstasjoner** er en indirekte relasjon som gjør det mulig å koble en kildeenhet til en målenhet via en eller flere andre *mellomenheter*.

Hvis for eksempel en aktivitetsenhet som heter *eCommerce_eCommercePurchasesWest* kobler til en midlertidig enhet kalt *eCommerce_eCommercePurchasesEast* og deretter kobler til en målenhet som heter *eCommerce_eCommerceContacts*, er det en relasjon med flere mellomstasjoner.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Kildeenhet kobler direkte til en målenhet med en midlertidig enhet.":::

### <a name="multi-hop-multi-path-relationship"></a>Relasjon med flere baner og flere mellomstasjoner

Relasjoner for flere mellomstasjoner og flere baner kan brukes sammen til å opprette **flere mellomstasjoner, flere baner**. Denne spesialtypen kombinerer funksjonene for **flere mellomstasjoner** og **relasjoner med flere baner**. Den lar deg koble til mer enn én målenhet når du bruker mellomliggende enheter.

Hvis for eksempel en aktivitetsenhet som heter *eCommerce_eCommercePurchasesWest* kobler til en midlertidig enhet kalt *eCommerce_eCommercePurchasesEast* og deretter kobler til to målenheter, både *eCommerce_eCommerceContacts* og *loyaltyScheme_loyCustomers*, er det en relasjon med flere mellomstasjoner og flere baner.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Kildeenhet kobler direkte til én målenhet og kobler til en annen målenhet via en mellomliggende enhet.":::

## <a name="next-step"></a>Neste trinn

Systemrelasjoner og egendefinerte relasjoner brukes til å [opprette segmenter](segments.md) og [målinger](measures.md) basert på flere datakilder som ikke lenger finnes i siloer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
