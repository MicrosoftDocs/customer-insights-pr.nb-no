---
title: Eksportere Customer Insights-data til Marketo
description: Lær hvordan du konfigurerer tilkoblingen til Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597983"
---
# <a name="connector-for-marketo-preview"></a>Kontakt for Marketo (forhåndsversjon)

Du kan eksportere segmenter av enhetlige kundeprofiler for å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Marketo.

## <a name="prerequisites"></a>Forutsetninger

-   Du har en [Marketo-konto](https://login.marketo.com/) og tilhørende påloggingsinformasjon for administrator.
-   Det finnes eksisterende lister i Marketo og de tilsvarende ID-ene. Hvis du vil ha mer informasjon, kan du se [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Du har [konfigurerte segmenter](segments.md).
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="connect-to-marketo"></a>Koble til Marketo

1. Gå til **Admin** > **Eksporter mål**.

1. Under **Marketo** velger du **Oppsett**.

1. Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.

1. Angi **[Marketo-klient-ID-en, klienthemmeligheten og vertsnavnet for REST-endepunktet](https://developers.marketo.com/rest-api/authentication/)**.

1. Angi **[ID-en for Marketo-listen](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Velg **Jeg godtar** for å bekrefte **datapersonvern og -samsvar**, og velg **Koble til** for å initialisere tilkoblingen til Marketo.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Skjermbilde for eksport av Marketo-tilkobling":::

1. Velg **Neste** for å konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurere koblingen

1. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. 

1. Du kan eventuelt eksportere **Fornavn**, **Etternavn**, **Poststed**, **Delstat** og **Land/område** som tilleggsfelt for å opprette mer tilpassede e-postmeldinger. Velg **Legg til attributt** for å tilordne disse feltene.

1. Velg segmentene du vil eksportere. Du kan eksportere opptil 1 million kundeprofiler totalt til Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Velg felt og segmenter som skal eksporteres til Marketo":::

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab). I Marketo kan du nå finne segmentene under [Marketo-lister](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million profiler per eksport til Marketo.
- Eksport til Marketo er begrenset til segmenter.
- Eksport av segmenter med totalt 1 million profiler kan ta opptil tre timer. 
- Antallet profiler du kan eksportere til Marketo, er avhengig av og begrenset til kontrakten din med Marketo.

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Marketo, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Marketo oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]