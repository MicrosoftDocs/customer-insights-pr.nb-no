---
title: Eksportere Customer Insights-data til Mailchimp
description: Lær hvordan du konfigurerer tilkoblingen til Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598213"
---
# <a name="connector-for-mailchimp-preview"></a>Kontakt for Mailchimp (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til MailChimp for å opprette nyhetsbrev og e-postkampanjer.

## <a name="prerequisites"></a>Forutsetninger

-   Du har en [Mailchimp-konto](https://mailchimp.com/) og tilhørende påloggingsinformasjon for administrator.
-   Det finnes eksisterende målgrupper i Mailchimp og de tilsvarende ID-ene. Hvis du vil ha mer informasjon, kan du se [målgrupper i Mailchimp](https://mailchimp.com/help/create-audience/).
-   Du har [konfigurerte segmenter](segments.md)
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="connect-to-mailchimp"></a>Koble til Mailchimp

1. Gå til **Admin** > **Eksporter mål**.

1. Under **Mailchimp** velger du **Oppsett**.

1. Gi eksportmålet et gjenkjennelig navn i **Visningsnavn**-feltet.

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Angi **[ID-en for Mailchimp-målgruppen](https://mailchimp.com/help/find-audience-id/)**, og velg **Koble til** for å initialisere tilkoblingen til Mailchimp.

1. Velg **Godkjenn med Mailchimp**, og angi Mailchimp-legitimasjonen din.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Skjermbilde for eksport av Mailchimp-tilkobling":::

1. Velg **Neste** for å konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurere koblingen

1. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. 

1. Du kan eventuelt eksportere **Fornavn** og **Etternavn** som tilleggsfelt for å opprette mer tilpassede e-postmeldinger. Velg **Legg til attributt** for å tilordne disse feltene.

1. Velg segmentene du vil eksportere. Du kan eksportere opptil 1 million kundeprofiler totalt til Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Velg felt og segmenter som skal eksporteres til MailChimp":::

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab). I Mailchimp kan du nå finne segmentene under [Mailchimp-målgrupper](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million profiler per eksport til Mailchimp.
- Eksport til Mailchimp er begrenset til segmenter.
- Eksport av segmenter med totalt 1 million profiler kan ta opptil tre timer på grunn av begrensninger på leverandørsiden. 
- Antallet profiler du kan eksportere til Mailchimp, er avhengig av og begrenset til kontrakten din med Mailchimp.

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Mailchimp, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Mailchimp oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]