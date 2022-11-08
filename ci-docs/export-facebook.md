---
title: Eksporter segmenter til Facebook Annonseadministrasjon (forhåndsversjon) (inneholder video)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Facebook Annonseadministrasjon.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724616"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Eksporter segmenter til Facebook Annonseadministrasjon (forhåndsversjon)

Eksporter segmenter for enhetlige kundeprofiler til Facebook Annonseadministrasjon for å opprette kampanjer på Facebook og Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Forutsetning

- En [Facebook-annonsekonto](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) som omfatter en [Facebook Business-konto](https://business.facebook.com/).
- Administratorrettigheter på [Facebook-annonsekontoen](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Egendefinerte målgruppevilkår må godtas av brukeren som konfigurerer tilkoblingen i Customer Insights.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 10 million kundeprofiler per eksport til Facebook Annonseadministrasjon, som kan ta opptil 90 minutter.
- Bare segmenter.
- Facebook-annonseintegrering støtter ikke brukere med flere enn 25 annonsekontoer.
- Typen Facebook-*kundeliste* i [egendefinerte målgrupper](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > I noen tilfeller vises kanskje egendefinerte målgrupper av forskjellige typer i rullegardinlisten. Hvis du velger en annen type enn *kundeliste*, mislykkes eksporten.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Konfigurer tilkobling til Facebook Annonseadministrasjon

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Facebook Annonseadministrasjon**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. [Tillat bidragsytere å bruke tilkoblingen for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Godkjenn med Facebook-annonser:

   1. Velg **Fortsett med Facebook** for å logge på Facebook-annonsekontoen.

   1. Tillat **ads_management**-tillatelsen etter godkjenning med Facebook.

   1. Velg **Facebook-annonsekontoen** du vil arbeide med.

   1. Velg en **Eksisterende egendefinert målgruppe** fra rullegardinlisten, eller opprett en **Ny tilpasset målgruppe**.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra delen Facebook Annonseadministrasjon i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. I feltet **Koble til data** velger du **E-post**, **Navn og adresse** eller **Telefon** som skal sendes til Facebook Annonseadministrasjon.

1. Tilordne de tilsvarende attributtene fra den enhetlige kundeenheten for den valgte nøkkelidentifikatoren.
   > [!TIP]
   > De beste mulighetene for et treff oppstår hvis du velger **E-post** som nøkkelidentifikator. Hvis du legger til flere identifikatorer, kan du få bedre samsvar.

1. Velg **Legg til attributt** for å tilordne flere attributter som skal sendes til Facebook Annonseadministrasjon. Attributter fra Facebook Annonseadministrasjon tilordnes til følgende brukervennlige navn: **FN** = **Fornavn**, **LN** = **Etternavn**, **FI** = **Første initial**, **PHONE** = **Telefon**, **GEN** = **Kjønn**, **DOB** = **Fødselsdato**, **ST** = **Delstat**, **CT** = **Postnummer**, **ZIP** = **Postnummer**, **COUNTRY** = **Land/distrikt**

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
