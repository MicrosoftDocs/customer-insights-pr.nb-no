---
title: Supplering av firmaprofiler med tredjeparts supplering fra Leadspace
description: Generell informasjon om tredjeparts supplering fra Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 08a4c56eb1c387015fd9e985a0c9484a13236fcf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646989"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Supplering av firmaprofiler med Leadspace (forhåndsversjon)

Leadspace er et datavitenskapsselskap som tilbyr en B-til-B-kundedataplattform. Det gjør det mulig for miljøer med enhetlige kundeprofiler, basert på forretningsforbindelser, å supplere dataene. Suppler *Kundeprofiler* med attributter som firmastørrelse, sted eller bransje. Suppler *Kontaktprofiler* med attributter som tittel, persona eller e-postbekreftelse.

## <a name="prerequisites"></a>Forutsetninger

Følgende forutsetninger må være oppfylt for at du skal kunne konfigurere Leadspace:

- Du har en aktiv Leadspace-lisens.
- Du har [enhetlige kundeprofiler](customer-profiles.md) basert på forretningsforbindelser.
- En Leadspace-tilkobling er allerede konfigurert av en administrator, eller du har [administrator](permissions.md#admin)-tillatelser og den "permanente nøkkelen" (kalt **Leadspace-token**). Kontakt [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) direkte hvis du vil ha mer informasjon om produktet.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**.

1. Velg **Suppler dataene** på Leadspace-flisen, og velg **Kom i gang**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skjermbilde av Leadspace-flisen.":::

1. Velg en [tilkobling](connections.md) fra rullegardinlisten. Kontakt en administrator hvis ingen tilkobling er tilgjengelig. Hvis du er en administrator, kan du opprette en tilkobling ved å velge **Legg til tilkobling** og deretter **Leadspace**. 

1. Velg **Koble til Leadspace** for å bekrefte tilkoblingen.

1. Velg **Neste**, og velg **kundedatasettet** du vil supplere med firmadata fra Leadspace. Du kan velge **kundeenheten** for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. Velg **Neste** og definer hvilken type felt fra de enhetlige profilene som skal brukes til å lete etter samsvarende firmadata fra Leadspace. Feltet **Navn på selskap** feltet er obligatorisk. For høyere nøyaktighet kan opptil to andre felter, **Selskapets nettsted** og **Selskapssted**, legges til.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Tilordningsrute i Leadspace-felt.":::

1. Velg **Neste** for å fullføre felttilordningen.

1. Merk av i avmerkingsboksen hvis du har *Kontaktprofiler* du vil supplere. Customer Insights vil automatisk tilordne de nødvendige feltene.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Kundekontaktsupplering i Leadspace.":::
 
1. Angi et navn for suppleringen, og velg **Lagre supplering** etter at du har sett gjennom valgene.


## <a name="configure-the-connection-for-leadspace"></a>Konfigurere tilkoblingen for Leadspace 

Du må være en administrator for å konfigurere tilkoblinger. Velg **Legg til tilkobling** når du konfigurerer en supplering *eller* gå til **Administrasjon** > **Tilkoblinger** og velg **Konfigurer** i Leadspace-flisen.

1. Velg **Komme i gang**. 

1. Skriv inn et navn på tilkoblingen i **Visningsnavn**-boksen.

1. Angi et gyldig Leadspace-token.

1. Gå gjennom og gi ditt samtykke til **Datapersonvern og -samsvar** ved å velge **Jeg er enig**.

1. Velg **Bekreft** for å validere konfigurasjonen.

1. Velg **Lagre** etter at verifiseringen er fullført.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Konfigurasjonsside for Leadspace-tilkobling.":::

## <a name="enrichment-results"></a>Resultater av supplering

Etter at du har oppdatert suppleringen, kan du gå gjennom de nylig supplerte firmadataene under [Mine suppleringer](enrichment-hub.md). Du kan finne tidspunktet for siste oppdatering og antall supplerte profiler.

Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.

Hvis du vil ha mer informasjon, kan du se [API-er for Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Neste trinn


[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til Leadspace, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Leadspace oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE [footer-include](includes/footer-banner.md)]