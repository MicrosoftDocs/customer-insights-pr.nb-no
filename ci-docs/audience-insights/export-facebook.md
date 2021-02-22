---
title: Eksportere Customer Insights-data til Facebook-annonseadministrasjon
description: Lær hvordan du konfigurerer tilkoblingen til Facebook-annonseadministrasjon.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643695"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Kobling for Facebook-annonseadministrasjon (forhåndsversjon)

Eksporter segmenter for enhetlige kundeprofiler til Facebook-annonseadministrasjon for å opprette kampanjer på Facebook og Instagram.

## <a name="prerequisites"></a>Forutsetninger

- Du må ha en [**Facebook-annonsekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) som inkluderer en [**Facebook-bedriftskonto**](https://business.facebook.com/).
- Du må være administrator på [**Facebook-annonsekontoen**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Koble til Facebook-annonseadministrasjon

1. Gå til **Admin** > **Eksporter mål**.

1. Under **Facebook-annonseadministrasjon** velger du **Konfigurer**.

1. Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.

1. Velg **Fortsett med Facebook** for å logge på Facebook-annonsekontoen din.

1. Tillat **ads_management**-tillatelsen etter godkjenning med Facebook.

1. Velg **Facebook-annonsekontoen** du vil arbeide med.

1. Velg en **eksisterende egendefinert målgruppe** fra rullegardinlisten, eller opprett et **ny egendefinert målgruppe**. Hvis du vil ha mer informasjon, kan du se [**Målgrupper i Facebook-annonseadministrasjon**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Neste** for å konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurere koblingen

1. I feltet **Velg nøkkelidentifikator** velger du **E-post**, **Navn og adresse** eller **Telefon** som skal sendes til Facebook-annonseadministrasjon.

1. Tilordne de tilsvarende attributtene fra den enhetlige kundeenheten for den valgte nøkkelidentifikatoren.
   > [TIPS] Den beste muligheten for et treff oppstår hvis du velger **E-post** som nøkkelidentifikator. Hvis du legger til flere identifikatorer, kan du få bedre samsvar.

1. Velg **Legg til attributt** for å tilordne flere attributter som skal sendes til Facebook-annonseadministrasjon. Attributter fra Facebook-administrasjon tilordnes til følgende brukervennlige navn: **FN** = **Fornavn**, **LN** = **Etternavn**, **FI** = **Første initial**, **PHONE** = **Telefon**, **GEN** = **Kjønn**, **DOB** = **Fødselsdato**, **ST** = **Delstat**, **CT** = **Poststed**, **ZIP** = **Postnummer**, **COUNTRY** = **Land/distrikt**

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Facebook-annonseadministrasjon, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Facebook-annonseadministrasjon oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.