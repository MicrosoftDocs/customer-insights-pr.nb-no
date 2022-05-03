---
title: Suppler kundeprofiler med stedsdata fra Azure Maps
description: Generell informasjon om førstepartssupplering for Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 6a1c3791076a7dda4531664ca88632f7f1b914e3
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646532"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Supplering av kundeprofiler med Azure Maps (forhåndsversjon)

Azure Maps tilbyr posisjonssentriske data og tjenester for å levere opplevelse basert på geospatiale data med innebygd posisjonsintelligens. Azure Maps-datasuppleringstjenester forbedrer presisjonen for posisjonsinformasjon om kundene. Den bringer funksjoner som adressenormalisering og bredde- og lengdegradsuttrekking til Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Forutsetninger

Følgende forhåndskrav må være oppfylt for å konfigurere Azure Maps-datasupplering:

- Du må ha et aktivt Azure Maps-abonnement. Hvis du vil ha et abonnement, kan du [registrere deg eller få en prøveversjon](https://azure.microsoft.com/services/azure-maps/).

- En Azure Maps-[tilkobling](connections.md) er tilgjengelig, *eller* du har [administrator](permissions.md#admin)tillatelser og en aktiv API-nøkkel for Azure Maps.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**. 

1. Velg **Suppler dataene** på **Posisjon**-flisen.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps-flis.":::

1. Velg en [tilkobling](connections.md) fra rullegardinlisten. Kontakt en administrator hvis ingen Azure Maps-tilkobling er tilgjengelig. Hvis du er en administrator, kan du [konfigurere tilkoblingen for Azure Maps](#configure-the-connection-for-azure-maps). 

1. Velg **Neste** for å bekrefte valget.

1. Velg **kundeoppføringsdatasettet** du vil supplere med posisjonsdata fra Azure Maps. Du kan velge enheten **Kunde** for å supplere alle de enhetlige kundeprofilene, eller velge en segmentenhet for å supplere bare kundeprofiler i det segmentet.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. Velg om du vil tilordne felter til hoved- eller sekundæradressen. Du kan angi en felttilordning for begge adressene og fylle inn profilene for begge adressene separat, for eksempel for en privatadresse og en forretningsadresse. Velg **Neste**.

1. Definer hvilke felter fra de enhetlige profilene som skal brukes til å se etter samsvarende posisjonsdata fra Azure Maps. Feltene **Gate/vei 1** og **Postnummer** kreves for den valgte primære eller sekundære adressen. Du kan legge til flere felter for å oppnå høyere samsvarsnøyaktighet.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Konfigurasjonsside for Azure Maps-supplering.":::

1. Velg **Neste** for å fullføre felttilordningen.

1. Vurder om du vil endre **Avanserte innstillinger**. Disse leveres for å gi maksimal fleksibilitet til å håndtere avanserte brukssaker, men standardverdiene vil i de fleste tilfeller være tilstrekkelige:
   - **Adressetype**: Standard virkemåte er at suppleringen returnerer den beste adressen, selv om den er ufullstendig. Hvis du bare vil ha fullstendige adresser, for eksempel adresser som inkluderer husnummeret, fjerner du merket i alle avmerkingsboksene unntatt **punktadresser**. 
   - **Språk**: Adresser returneres som standard på språket for området som det er fastslått at adressen skal tilhøre. Hvis du vil bruke et standardisert adressespråk, velger du språket på rullegardinmenyen. Hvis du for eksempel velger **Engelsk**, returneres **Copenhagen, Denmark** i stedet for **København, Danmark**.

1. Angi et navn for suppleringen.

1. Se gjennom valgene, og velg deretter **Lagre supplering**.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurer tilkoblingen for Azure Maps

Du må være en administrator i Customer Insights for å konfigurere tilkoblinger. Velg **Legg til tilkobling** når du konfigurerer en supplering eller gå til **Administrator** > **Tilkoblinger**, og velg **Konfigurer** på Azure Maps-flisen.

1. Skriv inn at navn på tilkoblingen i feltet **Visningsnavn**.

1. Angi en gyldig API-nøkkel for Azure Maps.

1. Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**

1. Velg **Bekreft** for å validere konfigurasjonen.

1. Velg **Lagre** etter at verifiseringen er fullført.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Konfigurasjonsside for Azure Maps-tilkobling.":::

## <a name="enrichment-results"></a>Resultater av supplering

Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen. Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab). Behandlingstiden avhenger av størrelsen på kundedataene og API-svartidene.

Når suppleringsprosessen er fullført, kan du se gjennom de nylig forbedrede kundeprofildataene under **Mine suppleringer**. I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.

Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du gjør det mulig for Dynamics 365 Customer Insights å overføre data til Azure Maps, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data som personlige data. Microsoft overfører slike data etter instruksjonen, men du er ansvarlig for å sørge for at Azure Maps oppfyller personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du gå til [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.

[!INCLUDE [footer-include](includes/footer-banner.md)]
