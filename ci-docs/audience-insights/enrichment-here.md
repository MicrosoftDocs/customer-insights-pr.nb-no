---
title: Berike med tredjeparts supplering fra HERE Technologies
description: Generell informasjon om tredjeparts supplering fra HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668690"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Supplering av kundeprofiler med HERE Technologies (forhåndsversjon)

HERE Technologies er et lokasjonsplattformfirma som tilbyr lokasjonssentrerte data og tjenester. Ved hjelp av tjenester for datasupplering fra HERE Technologies kan du bygge et mer nøyaktig stedsforståelse av kundene med adressenormalisering, bredde- og lengdegradsuttrekking og så videre.

## <a name="prerequisites"></a>Forutsetninger

For å konfigure HERE Technologies-suppleringer må følgende forhåndskrav være oppfylt:

- Du har et aktivt abonnement på HERE Technologies. Hvis du vil ha et abonnement, kan du [registrere deg her](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkte. [Finn ut mer om lokasjonssupplement fra HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Du har API-nøkkelen for HERE Technologies.

- Du har [administratortillatelser](permissions.md#administrator).

## <a name="configuration"></a>Konfigurasjon

1. Gå til **Data** > **Supplering**.

1. Velg **Suppler dataene** på HERE Technologies-flisen.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies-flis](media/HERE-tile.png "HERE Technologies-flis")

1. Angi en aktiv **API-nøkkel for HERE Technologies**. Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**. 

1. Bekreft begge inndataene ved å velge **Koble til HERE**.

1. Velg **Legg til data**, og velg om du vil tilordne felt til den primære og/eller sekundære adressen. Du kan angi en felttilordning for begge adressene (for eksempel en privatadresse og en firmaadresse), og du kan supplere profilene hver for seg. Velg **Neste**.

1. Definer hvilke felt fra de enhetlige profilene som skal brukes til å søke etter samsvarende stedsdata fra HERE Technologies. Feltene **Gate/vei 1** og **Postnummer** kreves for den valgte primære og/eller sekundære adressen. Flere felt kan legges til for å oppnå høyere nøyaktighet.

   > [!div class="mx-imgBorder"]
   > ![Konfigurasjonsside for HERE Technologies-supplering](media/enrichment-HERE-configuration.png "Konfigurasjonsside for HERE Technologies-supplering")

1. Velg **Bruk** for å fullføre felttilordningen.

## <a name="enrichment-results"></a>Resultater av supplering

Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen. Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab). Behandlingstiden avhenger av størrelsen på kundedataene og API-responstidene fra HERE Technologies.

Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**. I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.

Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.

## <a name="next-steps"></a>Neste trinn

Bygg på toppen av de supplerte kundedataene. Opprett [segmenter](segments.md), [mål](measures.md) og til og med [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til HERE Technologies, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at HERE Technologies oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.