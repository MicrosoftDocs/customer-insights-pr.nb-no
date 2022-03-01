---
title: Eksporter Customer Insights-data til AdRoll
description: Lær hvordan du konfigurerer tilkoblingen til AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697086"
---
# <a name="connector-for-adroll-preview"></a>Kontakt for AdRoll (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til AdRoll, og bruk dem for reklame. 

## <a name="prerequisites"></a>Forutsetninger

-   Du har en [AdRoll-konto](https://www.adroll.com/) og tilhørende legitimasjon for administrator.
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="connect-to-adroll"></a>Koble til AdRoll

1. Gå til **Admin** > **Eksporter mål**.

1. Under **AdRoll** velger du **Oppsett**.

1. Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfigurasjonsrute for AdRoll-tilkobling.":::

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til AdRoll.

1. Velg **Godkjenn med AdRoll**, og angi administratorlegitimasjonen din for AdRoll. 

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Angi **annonsør-ID-en din for AdRoll** [AdRoll-annonsør](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Velg **Neste** for å konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurere koblingen

1. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. Dette kreves for å eksportere segmenter til AdRoll.

1. Velg segmentene du vil eksportere. Velg et segment med minst 100 medlemmer. Du kan ikke eksportere mindre segmenter. I tillegg er maksimumsstørrelsen for et segment som skal eksporteres, 250 000 medlemmer per eksport. 

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 250 000 profiler per eksport til AdRoll.
- Du kan ikke eksportere segmenter med færre enn 100 profiler til AdRoll. 
- Eksport til AdRoll er begrenset til segmenter.
- Det kan ta opptil 10 minutter å eksportere opptil 250 000 profiler til AdRoll. 
- Antallet profiler du kan eksportere til AdRoll, er avhengig av og begrenset til kontrakten din med AdRoll.

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til AdRoll, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at AdRoll oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
