---
title: Berike med tredjeparts supplering fra Experian
description: Generell informasjon om tredjeparts supplering fra Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896385"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Supplere kundeprofiler med demografidata fra Experian (forhåndsversjon)

Experian er en global leder innen forbruker- og forretningskredittrapportering og markedsføringstjenester. Ved hjelp Experians datasuppleringstjenester kan du bygge opp en dypere forståelse av kundene ved å supplere kundeprofilene med demografiske data, for eksempel husholdningsstørrelse, inntekt og så videre.

## <a name="prerequisites"></a>Forutsetninger

For å konfigurere Experian må følgende forutsetninger være oppfylt:

- Du har et aktivt Experian-abonnement. Hvis du vil ha et abonnement, [kontakter du Experian](https://www.experian.com/marketing-services/contact) direkte. [Finn ut mer om Experian-datasupplering](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- En Experian-tilkobling er allerede konfigurert av en *administrator*, eller du har [administrator](permissions.md#administrator)-tillatelser. Du må også ha bruker-ID-en, parts-ID-en og modellnummeret for den SSH-aktiverte ST-kontoen (Secure Transport) som Experian opprettet for deg.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på Experian-flisen.

   > [!div class="mx-imgBorder"]
   > ![Experian-flis](media/experian-tile.png "Experian-flis")
   > 

1. Velg en [tilkobling](connections.md) fra rullegardinlisten. Kontakt en administrator hvis ingen tilkobling er tilgjengelig. Hvis du er en administrator, kan du opprette en tilkobling ved å velge **Legg til tilkobling** og velge Experian fra rullegardinlisten. 

1. Velg **Koble til Experian** for å bekrefte valget av tilkobling.

1.  Velg **Neste**, og velg **kundedatasettet** du vil supplere med demografiske data fra Experian. Du kan velge **kundeenheten** for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. Velg **Neste** og definer hvilken type felt fra de enhetlige profilene som skal brukes til å lete etter samsvarende demografiske data fra Experian. Minst ett av feltene **Navn og adresse**, **Telefon** eller **E-post** er obligatorisk. Hvis du vil ha høyere nøyaktighet for treff, kan du legge til opptil to andre felt. Dette valget påvirker tilordningsfeltene du har tilgang til i neste trinn.

    > [!TIP]
    > Flere nøkkel-ID-attributter som sendes til Experian, vil sannsynligvis gi en høyere samsvarsrate.

1. Velg **Neste** for å starte felttilordningen.

1. Definer hvilke felt fra de enhetlige profilene som skal brukes til å lete etter samsvarende demografiske data fra Experian. Obligatoriske felt er merket.

1. Angi et navn for suppleringen og et navn for utdataenheten.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

## <a name="configure-the-connection-for-experian"></a>Konfigurere tilkoblingen for Experian 

Du må være en administrator for å konfigurere tilkoblinger. Velg **Legg til tilkobling** når du konfigurerer en supplering *eller* gå til **Administrasjon** > **Tilkoblinger** og velg **Konfigurer** i Experian-filen.

1. Velg **Komme i gang**.

1. Skriv inn et navn på tilkoblingen i **Visningsnavn**-boksen.

1. Angi gyldig bruker-ID, parts-ID og modellnummer for Secure Transport-kontoen for Experian.

1. Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**

1. Velg **Bekreft** for å validere konfigurasjonen.

1. Velg **Lagre** etter at verifiseringen er fullført.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Rute for konfigurasjon av Experian-tilkobling.":::

## <a name="enrichment-results"></a>Resultater av supplering

Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen. Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab). Behandlingstiden avhenger av størrelsen på kundedataene og suppleringsprosessene som er satt opp for kontoen din av Experian.

Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**. I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.

Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.

## <a name="next-steps"></a>Neste trinn

Bygg på toppen av de supplerte kundedataene. Opprett [segmenter](segments.md), [mål](measures.md) og til og med [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Experian, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Experian oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
