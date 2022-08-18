---
title: Suppler kundeprofiler med HERE Technologies (forhåndsversjon)
description: Generell informasjon om tredjeparts supplering fra HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237870"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Suppler kundeprofiler med HERE Technologies (forhåndsversjon)

HERE Technologies er et lokasjonsplattformfirma som tilbyr lokasjonssentrerte data og tjenester. HERE Technologies' datasuppleringstjenester forbedrer presisjonen for stedsinformasjon om kundene. Den gir adressenormalisering, breddegrads- og lengdegradsuttrekking med mer.

## <a name="prerequisites"></a>Forutsetning

- Et aktivt HERE Technologies-abonnement. Hvis du vil ha et abonnement, [registrerer du deg her](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakter HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkte. [Finn ut mer om lokasjonssupplement fra HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- En HERE-[tilkobling](connections.md) er [konfigurert](#configure-the-connection-for-here-technologies) av en administrator.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurere tilkoblingen for HERE Technologies

Du må være en [administrator](permissions.md#admin) i Customer Insights og ha en aktiv API-nøkkel for HERE Technologies.

1. Velg **Legg til tilkobling** når du konfigurerer en supplering eller gå til **Administrasjon** > **Tilkoblinger** og velg **Konfigurer** i HERE technologies-filen.

1. Skriv inn et navn på tilkoblingen og en gyldig API-nøkkel for HERE Technologies.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Bekreft** for å validere konfigurasjonen, og velg deretter **Lagre**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Konfigurasjonsside for HERE Technologies-tilkobling.":::

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på **Sted** fra HERE Technologies-flisen.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies-flis.":::

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Velg tilkoblingen. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Velg **Neste**.

1. Velg **Kundedatasett** og velg profilen eller segmentet du vil supplere med data fra HERE Technologies. *Kunde*-enheten supplerer alle kundeprofilene dine, mens segmentsuppleringer bare supplerer kundeprofiler i det segmentet.

1. Definer hvilken type felter fra de enhetlige profilene som skal brukes til samsvar: primær- eller sekundæradressen. Du kan angi en felttilordning for begge adressene og supplere profilene for begge adressene separat. For eksempel en hjemmeadresse og en jobbadresse. Velg **Neste**.

1. Tildel feltene til firmadataene fra HERE Technologies. Feltene **Gate/vei 1** og **Postnummer** kreves for den valgte primære og/eller sekundære adressen. Hvis du vil ha høyere samsvarsnøyaktighet, legger du til flere felter.

1. Velg **Neste** for å fullføre felttilordningen.

1. Angi et **Navn** for suppleringen og **Utdataenhetsnavn**.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

1. Velg **Kjør** for å starte suppleringsprosessen, eller lukk for å gå tilbake til siden **Suppleringer**.

## <a name="view-enrichment-results"></a>Vis suppleringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antall kunder supplert av feltet** gir en neddrilling i dekningen av hvert supplerte felt.

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
