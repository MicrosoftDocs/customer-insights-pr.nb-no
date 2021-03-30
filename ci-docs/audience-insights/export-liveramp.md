---
title: LiveRamp-kobling
description: Lær hvordan du eksporterer data til LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597569"
---
# <a name="liverampreg-connector-preview"></a>Kobling for LiveRamp&reg; (forhåndsvisning)

Aktiver dataene i LiveRamp for å koble til over 500 plattformer på tvers av digitale og sosiale systemer og TV-økosystemer. Du kan arbeide med dataene dine i LiveRamp for å målrette, undertrykke og tilpasse annonsekampanjer.

## <a name="prerequisites"></a>Forutsetninger

- Du må ha et LiveRamp-abonnement for å bruke denne koblingen.
- Hvis du vil ha et abonnement, [kontakter du LiveRamp](https://liveramp.com/contact/) direkte. [Finn ut mer om LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Koble til LiveRamp

1. I Målgruppeinnsikt går du til **Administrasjon** > **Eksportmål**.

1. I **LiveRamp**-flisen velger du **Oppsett**.

1. Gi målet et gjenkjennelig navn i feltet **Visningsnavn**.

1. Angi et **brukernavn** og **passord** for din LiveRamp sikker FTP (SFTP)-konto.
Denne legitimasjonen kan være forskjellig fra din LiveRamp Onboarding-legitimasjon.

1. Velg **Bekreft** for å teste tilkoblingen til LiveRamp.

1. Etter vellykket verifisering må du gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**.

1. Velg **Neste** for å konfigurere LiveRamp-koblingen.

## <a name="configure-the-connector"></a>Konfigurere koblingen

1. I feltet **Velg nøkkelidentifikator** velger du **E-post**, **Navn og adresse** eller **Telefon** for å sende til LiveRamp for identitetsløsning.

1. Tilordne de tilsvarende attributtene fra den enhetlige kundeenheten for den valgte nøkkelidentifikatoren.

1. Velg **Legg til attributt** for å tilordne flere attributter som skal sendes til LiveRamp.

   > [!TIP]
   > Det å sende flere nøkkelidentifikatorattributter til LiveRamp gir deg sannsynligvis en høyere samsvarsrate.

1. Velg segmentene du vil eksportere til LiveRamp.

1. Velg **Lagre**.

> [!div class="mx-imgBorder"]
> ![LiveRamp-kobling med attributtilordning](media/export-liveramp-segments.png "LiveRamp-kobling med attributtilordning")

## <a name="export-the-data"></a>Eksportere dataene

Eksporten starter om kort tid hvis alle forhåndskravene for eksport er fullført. Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).
Når eksporten er fullført, kan du logge på LiveRamp Onboarding for å aktivere og distribuere dataene.

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til LiveRamp, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at LiveRamp oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.

[!INCLUDE[footer-include](../includes/footer-banner.md)]