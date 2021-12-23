---
title: Eksportere Customer Insights-data til Facebook Ads Manager (video)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4b2dc2ff8e5286209bd2ec94df42e82f0944715c
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/10/2021
ms.locfileid: "7904176"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Eksportere segmentlister til Facebook Ads Manager (forhåndsvisning)

Eksporter segmenter for enhetlige kundeprofiler til Facebook-annonseadministrasjon for å opprette kampanjer på Facebook og Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Forutsetninger for tilkobling

- Du må ha en [**Facebook-annonsekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) som inkluderer en [**Facebook-forretningskonto**](https://business.facebook.com/).
- Du må være en administrator på [**Facebook Ads-kontoen**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 10 millioner kundeprofiler per eksport til Facebook Ads Manager.
- Eksport til Facebook Ads Manager er begrenset til segmenter.
- Opprett eller oppdater egendefinerte målgrupper i Facebook bare av typen *kundeliste*.
- Det kan ta opptil 90 minutter å eksportere segmenter med totalt 10 million kundeprofiler.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Konfigurer tilkobling til Facebook Ads Manager

Før brukere kan opprette en eksport, må en administrator konfigurere tilkoblingen til tjenesten og la bidragsytere bruke tilkoblingen.

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Facebook Ads Manager** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Godkjenn med Facebook-annonser: 

   1. Velg **Fortsett med Facebook** for å logge på Facebook Ads-kontoen.

   1. Tillat **ads_management**-tillatelsen etter godkjenning med Facebook.

   1. Velg **Facebook-annonsekontoen** du vil arbeide med.

   1. Velg en **Eksisterende egendefinert målgruppe** fra rullegardinlisten, eller opprett en **Ny tilpasset målgruppe**. Hvis du vil ha mer informasjon, kan du se [**Målgrupper i Facebook-annonseadministrasjon**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Du kan bare opprette eller oppdatere egendefinerte målgrupper på Facebook av typen *kundeliste* med denne eksporten. I noen tilfeller ser du egendefinerte målgrupper av forskjellige typer i rullegardinlisten. Hvis du velger en annen type enn *kundeliste*, fører det til en mislykket eksport. 

1. Se gjennom **Datapersonvern og -samsvar**, og velg **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport. 

1. I **Tilkobling for eksport** velger du en tilkobling fra delen **Facebook Ads Manager**. Hvis navnet på denne delen ikke vises, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. I feltet **Velg nøkkelidentifikator** velger du **E-post**, **Navn og adresse** eller **Telefon** som skal sendes til Facebook-annonseadministrasjon. 

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet.

1. Tilordne de tilsvarende attributtene fra den enhetlige kundeenheten for den valgte nøkkelidentifikatoren.
   > [!TIP]
   > De beste mulighetene for et treff oppstår hvis du velger **E-post** som nøkkelidentifikator. Hvis du legger til flere identifikatorer, kan du få bedre samsvar.

1. Velg **Legg til attributt** for å tilordne flere attributter som skal sendes til Facebook Ads Manager. Attributter fra Facebook-administrasjon tilordnes til følgende brukervennlige navn: **FN** = **Fornavn**, **LN** = **Etternavn**, **FI** = **Første initial**, **PHONE** = **Telefon**, **GEN** = **Kjønn**, **DOB** = **Fødselsdato**, **ST** = **Delstat**, **CT** = **Postnummer**, **ZIP** = **Postnummer**, **COUNTRY** = **Land/distrikt**

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). 

Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Facebook-annonseadministrasjon, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Facebook-annonseadministrasjon oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å avslutte bruken av denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
