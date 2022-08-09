---
title: Suppler firmaprofiler med Leadspace (forhåndsversjon)
description: Generell informasjon om tredjeparts supplering fra Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 3f23fe7177f931db3e3179970915d0cd3c736f87
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196222"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Suppler firmaprofiler med Leadspace (forhåndsversjon)

Leadspace er et datavitenskapsselskap som tilbyr en B-til-B-kundedataplattform. Det gjør det mulig for miljøer med enhetlige kundeprofiler, basert på forretningsforbindelser, å supplere dataene. Suppler *Kundeprofiler* med attributter som firmastørrelse, sted eller bransje. Suppler *Kontaktprofiler* med attributter som tittel, persona eller e-postbekreftelse.

## <a name="prerequisites"></a>Forutsetning

- En aktiv Leadspace-lisens.
- [Enhetlige kundeprofiler](customer-profiles.md) basert på kontoer.
- En Leadspace-[tilkobling](connections.md) er [konfigurert](#configure-the-connection-for-leadspace) av en administrator. Kontakt [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) direkte hvis du vil ha mer informasjon om produktet.

## <a name="configure-the-connection-for-leadspace"></a>Konfigurere tilkoblingen for Leadspace

Du må være en [administrator](permissions.md#admin) i Customer Insights og ha den «permanente nøkkelen» (referert til som **Leadspace-token**).

1. Velg **Legg til tilkobling** når du konfigurerer en supplering eller gå til **Administrasjon** > **Tilkoblinger** og velg **Konfigurer** i Leadspace-flisen.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Konfigurasjonsside for Leadspace-tilkobling.":::

1. Skriv inn et navn på tilkoblingen og et gyldig Leadspace-token.

1. Gå gjennom og gi ditt samtykke til [Datapersonvern og -samsvar](#data-privacy-and-compliance) ved å velge **Jeg er enig**.

1. Velg **Bekreft** for å validere konfigurasjonen, og velg deretter **Lagre**.

### <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Leadspace, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Leadspace oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på **firmadataene** fra Leadspace-flisen.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skjermbilde av Leadspace-flisen.":::

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Velg tilkoblingen. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Velg **Neste**.

1. Velg **Kundedatasett** og velg profilen eller segmentet du vil supplere med firmadata fra Leadspace. *Kunde*-enheten supplerer alle kundeprofilene dine, mens segmentsuppleringer bare supplerer kundeprofiler i det segmentet.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. Definer hvilken type felter fra de enhetlige profilene som skal brukes til samsvar: primær- eller sekundæradressen. Du kan angi en felttilordning for begge adressene og supplere profilene for begge adressene separat. For eksempel en hjemmeadresse og en jobbadresse. Velg **Neste**.

1. Tildel feltene til firmadataene fra Leadspace. Feltet **Navn på selskap** feltet er obligatorisk. For høyere nøyaktighet kan opptil to andre felter, **Selskapets nettsted** og **Selskapssted**, legges til.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Tilordningsrute i Leadspace-felt.":::

1. Velg **Neste** for å fullføre felttilordningen.

1. Merk av i avmerkingsboksen hvis du har *Kontaktprofiler* du vil supplere. Customer Insights vil automatisk tilordne de nødvendige feltene.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Kundekontaktsupplering i Leadspace.":::

1. Velg **Neste**.

1. Angi et **Navn** for suppleringen og **Utdataenhetsnavn**.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

1. Velg **Kjør** for å starte suppleringsprosessen, eller lukk for å gå tilbake til siden **Suppleringer**.

## <a name="view-enrichment-results"></a>Vis suppleringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Hvis du vil ha mer informasjon, kan du se [API-er for Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
