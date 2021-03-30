---
title: Eksportere Customer Insights-data til DotDigital
description: Lær hvordan du konfigurerer tilkoblingen til DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598029"
---
# <a name="connector-for-dotdigital-preview"></a>Kontakt for DotDigital (forhåndsversjon)

Eksporter segmenter med enhetlige kundeprofiler til DotDigital-adressebøker, og bruk dem for kampanjer, e-postmarkedsføring og til å bygge kundesegmenter med DotDigital. 

## <a name="prerequisites"></a>Forutsetninger

-   Du har en [DotDigital-konto](https://dotdigital.com/) og tilhørende påloggingsinformasjon for administrator.
-   Det finnes eksisterende adressebøker i DotDigital og de tilsvarende ID-ene. Du kan finne ID-en i URL-adressen når du velger og åpner en adressebok. Hvis du vil ha mer informasjon, kan du se [DotDigital-adressebøker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="connect-to-dotdigital"></a>Koble til DotDigital

1. Gå til **Admin** > **Eksporter mål**.

1. Under **DotDigital** velger du **Oppsett**.

1. Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigurasjonsrute for DotDigital-eksport.":::

1. Angi **brukernavnet og passordet for DotDigital**.

1. Angi **[ID-en for DotDigital-adresseboken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til DotDigital.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Neste** for å konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurere koblingen

1. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**, **Fullt navn**, **Kjønn** og **Postnummer**.

1. Velg segmentene du vil eksportere. Du kan eksportere opptil 1 million kundeprofiler totalt til DotDigital.

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab). I DotDigital kan du nå finne segmentene i [DotDigital-adressebøker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million profiler per eksport til DotDigital.
- Eksport til DotDigital er begrenset til segmenter.
- Eksport av segmenter med totalt 1 million profiler kan ta opptil tre timer på grunn av begrensninger på leverandørsiden. 
- Antallet profiler du kan eksportere til DotDigital, er avhengig av og begrenset til kontrakten din med DotDigital.

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til DotDigital, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at DotDigital oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]