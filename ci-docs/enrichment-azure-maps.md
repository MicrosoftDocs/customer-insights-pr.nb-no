---
title: Suppler kundeprofiler med stedsdata fra Azure Maps (forhåndsversjon)
description: Generell informasjon om førstepartssupplering for Azure Maps.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238054"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Suppler kundeprofiler med stedsdata fra Azure Maps (forhåndsversjon)

Azure Maps tilbyr stedsentriske data og tjenester for å levere opplevelser basert på geospatiale data med innebygd stedsintelligens. Azure Maps-datasuppleringstjenester forbedrer presisjonen for posisjonsinformasjon om kundene. Den bringer funksjoner som adressenormalisering og bredde- og lengdegradsuttrekking til Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Forutsetning

- Et aktivt Azure Maps-abonnement. [Registrer deg for en prøveversjon](https://azure.microsoft.com/services/azure-maps/) for å få et abonnement.

- En Azure Maps-[tilkobling](connections.md) er [konfigurert](#configure-the-connection-for-azure-maps) av en administrator.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurer tilkoblingen for Azure Maps

Du må være en [administrator](permissions.md#admin) i Customer Insights og ha en aktiv API-nøkkel for Azure Maps.

1. Velg **Legg til tilkobling** når du konfigurerer en supplering eller gå til **Administrator** > **Tilkoblinger**, og velg **Konfigurer** på Azure Maps-flisen.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Konfigurasjonsside for Azure Maps-tilkobling.":::

1. Skriv inn et navn på tilkoblingen og en gyldig API-nøkkel for Azure Maps.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Bekreft** for å validere konfigurasjonen, og velg deretter **Lagre**.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på **Sted** fra Microsoft Azure Maps-flisen.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps-flis.":::

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Velg tilkoblingen. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Velg **Neste**.

1. Velg **Kundedatasett** og velg profilen eller segmentet du vil supplere med data fra Microsoft. *Kunde*-enheten supplerer alle kundeprofilene dine, mens segmentsuppleringer bare supplerer kundeprofiler i det segmentet.

1. Definer hvilken type felter fra de enhetlige profilene som skal brukes til samsvar: primær- eller sekundæradressen. Du kan angi en felttilordning for begge adressene og supplere profilene for begge adressene separat. For eksempel en hjemmeadresse og en jobbadresse. Velg **Neste**.

1. Tildel feltene til stedsdata fra Azure Maps. Feltene **Gate/vei 1** og **Postnummer** kreves for den valgte primære og/eller sekundære adressen. Hvis du vil ha høyere samsvarsnøyaktighet, legger du til flere felter.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Attributtildeling for Azure Maps.":::

1. Velg **Neste** for å fullføre felttilordningen.

1. Gå gjennom **Avanserte innstillinger**, som gir maksimal fleksibilitet til å håndtere avanserte brukssaker. Standardverdiene nedenfor trenger vanligvis ikke å endres.

   - **Adressetype**: Beste adressesamsvar returneres selv om den er ufullstendig. Hvis du bare vil ha fullstendige adresser, for eksempel adresser som inkluderer husnummeret, fjerner du merket i alle avmerkingsboksene unntatt **punktadresser**.
   - **Språk**: Adresser returneres på språket basert på adresseområdet. Hvis du vil bruke et standardisert adressespråk, velger du språket på rullegardinmenyen. Hvis du for eksempel velger **Engelsk**, returneres **Copenhagen, Denmark** i stedet for **København, Danmark**.
   - **Maksimalt antall resultater**: Antall resultater per adresse.

1. Velg **Neste**.

1. Angi et **Navn** for suppleringen og **Utdataenhetsnavn**.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

1. Velg **Kjør** for å starte suppleringsprosessen, eller lukk for å gå tilbake til siden **Suppleringer**.

## <a name="view-enrichment-results"></a>Vis suppleringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antall kunder supplert av feltet** gir en neddrilling i dekningen av hvert supplerte felt.

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
