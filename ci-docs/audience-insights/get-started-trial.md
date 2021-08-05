---
title: Opprett og konfigurer en prøveversjon for Customer Insights
description: Fremgangsmåte for å få et prøveversjonsabonnement for Dynamics 365 Customer Insights og konfigurere det.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f80654f03252142ce08241ff3ca3606be4595740
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650495"
---
# <a name="set-up-a-trial-environment"></a>Konfigurer et prøveversjonsmiljø 

Med en prøveversjon av Dynamics 365 Customer Insights kan du se gjennom nøkkelfunksjonene og finne ut mer om de forskjellige funksjonene. Et prøveversjonsabonnement slettes etter at det er utløpt. Prøveversjonsmiljøer opprettes av enkeltbrukere som blir administrator av prøveversjonsmiljøet. De kan invitere flere brukere til prøveversjonen og konfigurere de forskjellige funksjonene.

## <a name="create-a-trial-environment"></a>Opprette et prøvemiljø

Du kan registrere deg for en prøveversjon på [registreringssiden for prøveversjon](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Velg alternativet for **Registrer deg for en gratis prøveversjon**, og velg **Registrer deg nå**.

1. Oppgi e-postadressen for jobb eller skole, fortell oss mer om deg selv og velg **Kom i gang**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogen for å registrere deg for en prøveversjonsforekomst":::

1. Se gjennom vilkårene, og velg deretter **Fortsett** for å bekrefte.

1. Angi et **Navn** på det nye miljøet. 

1. Angi miljøet **Type** som **prøveversjon**.

1. I feltet **Velg en bransjedemo** kan du eventuelt velge et bransjespesifikk datasett. Du kan også [bytte til en bransjedemo](#use-industry-specific-demo-data-sets-in-audience-insights) senere og starte med standard datasett.

1. Velg **Område** for miljøet ditt.

1. Hvis du er administrator for en Dynamics 365-organisasjon: Velg **Avanserte innstillinger** og oppgi nettadressen til organisasjonen for å bruke prediksjonsfunksjoner som prediksjon for kundefrafall. 

1. Velg **Opprett**. 

Det tar noen få minutter å fullføre miljøinstallasjonen. Etter ferdigstillelse blir du omdirigert til demomiljøet eller bransjedemoen du velger i trinnet ovenfor. Du kan nå utforske appen med skrivebeskyttede demodata. Hvis du vil legge til dine egne data i miljøet, kan du se [Opprett scenariospesifikke demodata i ditt eget miljø](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Skjermbilde av et nylig opprettet prøveversjonsmiljø.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Bruk bransjespesifikke demodatasett i målgruppeinnsikt

Tilkobling av reelle datakilder er et av de viktigste trinnene for å bruke kraften i Customer Insights. Hvis du vil prøve funksjoner uten å forstyrre dine egne data, kan du eventuelt bruke bransjespesifikke demodata. Det er et par demodatasett tilgjengelige for følgende bransjer: 

-   Bil
-   Bankvirksomhet
-   Forbrukervarer
-   Offentlig sektor
-   Helsevesen
-   Representasjon
-   Forsikring
-   Produksjon
-   Profesjonelle tjenester
-   Detaljhandel

### <a name="see-industry-specific-demo-data-in-trials"></a>Se bransjespesifikke demodata i prøveversjoner

Hvis du vil ha en skrivebeskyttet versjon av Customer Insights, skreddersydd for en bestemt bransje eller et bestemt scenario, starter du i demomiljøet. 
 
1.  Velg **demomiljøet** i miljøvelgeren i målgruppeinnsikt.

2.  På **Start** velger du et alternativ på rullegardinmenyen Velg en bransjedemo.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Velg en bransje for prøveversjonsmiljøet.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Opprett scenariospesifikke demodata i ditt eget miljø

Som en administrator velger du miljøvelgeren i appoverskriften for å opprette et nytt miljø. I det nye miljøet kan du konfigurere dine egne datakilder og konfigurere appen i henhold til dine krav. 

1.  I Målgruppeinnsikt går du til **Data** > **Datakilder**.

2.  Hvis du vil importere dine egne datakilder, går du til [veiledningen for datainntak](data-sources.md).     
   Hvis du foretrekker å arbeide med eksempeldata som lar deg prøve ut datainntak, kan du innta bransjedemodataene i miljøet ditt. Velg alternativet **Importer fra Datahub** og følg trinnene nedenfor.

3.  Velg bransjekortet som passer til ditt scenario. 

4.  Se gjennom og eventuelt oppdatere det foreslåtte navnet på datakilde. 

5.  Velg **Neste** for å innta eksempeldataene. 

Du kan nå bruke de inntatte dataene til å skreddersy Customer Insights til scenariet. Hvis du vil se et miljø som er spesifikt for de inntatte demodataene, velger du **<Industry>Demo**-alternativet i miljøvelgeren.

## <a name="limitations-in-trials"></a>Begrensninger i prøveversjoner

- Prøveversjoner er aktive i 30 dager som standard. Du kan imidlertid utvide dem etter dag 23 når du logger på prøveversjonen.
- Du kan ikke bruke din egen Azure Data Lake-lagringskonto til å lagre utdata under en prøveversjon. Du kan imidlertid innta data fra en Data Lake-lagringskonto.
- Du kan lagre opptil 3 GB data i Dataverse-miljøet som klargjøres automatisk når du starter en Customer Insights-prøveversjon.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Kopier data fra en prøveversjon til et betalt abonnement

Generelt anbefaler vi at du starter på nytt med dine egne data når du oppgraderer til den betalte versjonen av Customer Insights. 

Du kan eventuelt kopiere dataene dine fra et prøveversjonsmiljø hvis du kjøper Customer Insights. Du må være administrator for prøveversjonen av Customer Insights og den globale administratoren for Microsoft 365-leieren, eller Dynamics 365-administrator i organisasjonen for å overføre innstillingene fra et prøveversjonsmiljø til et betalt miljø. 

Etter at du har logget på den betalte forekomsten av Customer Insights for første gang, blir du bedt om å opprette et nytt miljø. I denne prosessen kan du velge å kopiere konfigurasjonen fra et eksisterende miljø og overføre de fleste innstillingene. Hvis du har tillatelsene nevnt ovenfor, vises prøveversjonsmiljøet i denne listen. Hvis du vil ha mer informasjon, kan du se [Kopier miljøkonfigurasjonen](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Neste trinn

Se gjennom følgende artikler for å hjelpe deg med å komme i gang med konfigureringen av Customer Insights. 

- [Legg til flere brukere og tilordne tillatelser](permissions.md).
- [Innta datakildene](data-sources.md) og kjør dem gjennom [dataforeningsprosessen](data-unification.md) for å få [enhetlige kundeprofiler](customer-profiles.md).
- [Suppler de enhetlige kundeprofilene](enrichment-hub.md) eller [kjør prediktive modeller](predictions-overview.md).
- Opprett [segmenter](segments.md) for å gruppere kunder og nøkkelindikatorer for [målgjennomgang](measures.md).
- Konfigurer [tilkoblinger](connections.md) og [eksporter](export-destinations.md) for å behandle delsett av dataene i andre programmer.