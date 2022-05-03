---
title: Berikelse med tredjeparts supplering fra HERE Technologies
description: Generell informasjon om tredjeparts supplering fra HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c131ffb230a62b76e123334ff3c6776c8f9aa06e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646820"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Supplering av kundeprofiler med HERE Technologies (forhåndsversjon)

HERE Technologies er et lokasjonsplattformfirma som tilbyr lokasjonssentrerte data og tjenester. Ved hjelp av tjenester for datasupplering fra HERE Technologies kan du bygge et mer nøyaktig stedsforståelse av kundene med adressenormalisering, bredde- og lengdegradsuttrekking og så videre.

## <a name="prerequisites"></a>Forutsetninger

For å konfigure HERE Technologies-suppleringer må følgende forhåndskrav være oppfylt:

- Du har et aktivt abonnement på HERE Technologies. Hvis du vil ha et abonnement, kan du [registrere deg her](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkte. [Finn ut mer om lokasjonssupplement fra HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- En HERE [-tilkobling](connections.md) er tilgjengelig, *eller* du har [administrator](permissions.md#admin)- tillatelser og API-nøkkelen for HERE Technologies.

## <a name="configure-the-enrichment"></a>Konfigurere suppleringen

1. Gå til **Data** > **Supplering**. 

1. Velg **Suppler dataene** på HERE Technologies-flisen, og velg **Kom i gang**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies-flis.](media/HERE-tile.png "HERE Technologies-flis")

1. Velg en [tilkobling](connections.md) fra rullegardinlisten. Kontakt en administrator hvis ingen tilkobling er tilgjengelig. Hvis du er en administrator, kan du opprette en tilkobling ved å velge **Legg til tilkobling**. Velg **HERE Technologies** i rullegardinlisten. 

1. Velg **Koble til HERE Technologies** for å bekrefte valget.

1.  Velg **Neste**, og velg **kundedatasettet** du vil supplere med stedsdata fra HERE Technologies. Du kan velge **kundeenheten** for å forbedre alle kundeprofilene dine, eller velge en segmentenhet som bare skal supplere kundeprofiler i det segmentet.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Skjermbilde når du velger kundedatasettet.":::

1. Velg om du vil tilordne felter til den primære og/eller sekundære adressen. Du kan angi en felttilordning for begge adressene og supplere profilene for begge adressene separat. Hvis det for eksempel finnes en hjemme- og en forretningsadresse. Velg **Neste**.

1. Definer hvilke felt fra de enhetlige profilene som skal brukes til å søke etter samsvarende stedsdata fra HERE Technologies. Feltene **Gate/vei 1** og **Postnummer** kreves for den valgte primære og/eller sekundære adressen. Flere felt kan legges til for å oppnå høyere nøyaktighet.

   > [!div class="mx-imgBorder"]
   > ![Konfigurasjonsside for HERE Technologies-supplering.](media/enrichment-HERE-configuration.png "Konfigurasjonsside for HERE Technologies-supplering")

1. Velg **Neste** for å fullføre felttilordningen.

1. Angi et navn for suppleringen. 

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurere tilkoblingen for HERE Technologies 

Du må være en administrator for å konfigurere tilkoblinger. Velg **Legg til tilkobling** når du konfigurerer en supplering *eller* gå til **Administrasjon** > **Tilkoblinger** og velg **Konfigurer** i HERE technologies-filen.

1. Skriv inn et navn på tilkoblingen i **Visningsnavn**-boksen.

1. Angi en gyldig API-nøkkel for HERE Technologies.

1. Gå gjennom og gi ditt samtykke til **Datapersonvern og -samsvar** ved å velge **Jeg er enig**.

1. Velg **Bekreft** for å validere konfigurasjonen.

1. Velg **Lagre** etter at verifiseringen er fullført.

   > [!div class="mx-imgBorder"]
   > ![Konfigurasjonsside for HERE Technologies-tilkobling.](media/enrichment-HERE-connection.png "Konfigurasjonsside for HERE technologies-tilkobling")

## <a name="enrichment-results"></a>Resultater av supplering

Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen. Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab). Behandlingstiden avhenger av størrelsen på kundedataene og API-responstidene fra HERE Technologies.

Når suppleringsprosessen fullføres, kan du se gjennom de nylig klargjorte kundeprofildataene under **Mine suppleringer**. I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.

Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til HERE Technologies, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at HERE Technologies oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne denne suppleringen når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE [footer-include](includes/footer-banner.md)]
