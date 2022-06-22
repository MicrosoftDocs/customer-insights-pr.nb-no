---
title: Hentee data via en Power Query-tilkobling (inneholder video)
description: Koblinger for datakilder basert på Power Query.
ms.date: 05/09/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: b99c3b446e580f455f9678d54d9db414aea9b331
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011669"
---
# <a name="connect-to-a-power-query-data-source"></a>Koble til en Power Query-datakilde

Power Query har et bredt sett med koblinger som kan brukes til å legge inn data. De fleste av disse koblingene støttes av Dynamics 365 Customer Insights.

Når du legger til datakilder basert på Power Query-koblinger, følger du trinnene som beskrives i denne delen. Avhengig av hvilken kontakt du bruker, er det imidlertid nødvendig med forskjellig informasjon. Hvis du vil vite mer, kan du se dokumentasjonen for individuelle koblinger i [Power Query-koblingsreferansen](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Opprette en ny datakilde

1. Gå til **Data** > **Datakilder**.

1. Velg **Legg til datakilde**.

1. Velg **Microsoft Power Query**.

1. Angi et **navn** og en valgfri **beskrivelse** for datakilden, og velg **Neste**.

1. Velg én av de [tilgjengelige koblingene](#available-power-query-data-sources). I dette eksemplet velger vi **Tekst-/CSV**-koblingen.

1. Angi de nødvendige detaljene i **Tilkoblingsinnstillinger** for den valgte koblingen, og velg **Neste** for å vise en forhåndsvisning av dataene.

1. Velg **Transformere data**. I dette trinnet skal du legge til enheter i datakilden. Enheter er datasett. Hvis du har en database som inneholder flere datasett, er hvert datasett sin egen enhet.

1. Med dialogboksen **Power Query - Rediger spørringer** kan du se gjennom og finjustere dataene. Enhetene som systemene identifiserte i den valgte datakilden, vises i venstre rute.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dialogboksen Rediger spørringer":::

1. Du kan også endre dataene dine. Velg en enhet som skal redigeres eller transformeres. Bruk alternativene i vinduet Power Query til å bruke transformasjoner. Hver transformasjon vises under **Brukte trinn**. Power Query inneholder en rekke forhåndsbygde transformasjonsalternativer. Hvis du vil ha mer informasjon, kan du se [Power Query-transformasjoner](/power-query/power-query-what-is-power-query#transformations).

   Vi anbefaler at du bruker følgende transformasjoner:

   - Hvis du heter data fra en CSV-fil, inneholder den første raden ofte overskrifter. Gå til **Transformasjon** og velg **Bruk første rad som overskrifter**.
   - Kontroller at datatypen er angitt riktig. For datofelt velger du for eksempel en datotype.

1. Hvis du vil legge til flere enheter i datakilde i dialogboksen **Rediger spørringer**, går du til **Hjem** og velger **Hent data**. Gjenta trinn 6 til 10 til du har lagt til alle enhetene for denne datakilde.

1. Velg **Lagre**. Siden **Datakilder** åpnes med den nye datakilde i statusen **Oppdaterer**.

### <a name="available-power-query-data-sources"></a>Tilgjengelige Power Query-datakilder

Se [Power Query-koblingsreferansen](/power-query/connectors/) for en liste over koblinger som du kan bruke til å importere data til Customer Insights.

Koblinger med et merke i kolonnen **Customer Insights (dataflyter)** er tilgjengelige for oppretting av nye datakilder basert på Power Query. Se gjennom dokumentasjonen for en bestemt kobling for å finne ut mer om dens forhåndskrav, [spørringsbegrensninger](/power-query/power-query-online-limits) og andre detaljer.

## <a name="add-data-from-on-premises-data-sources"></a>Legge til data fra lokale datakilder

Inntak av data fra lokale datakilder støttes basert på Microsoft Power Platform-dataflyter (PPDF-er). Du kan aktivere dataflyter i Customer Insights ved [å angi Microsoft Dataverse-nettadressen for miljøet](create-environment.md) når du konfigurerer miljøet.

Datakilder som opprettes etter at et miljø er knyttet til et Dataverse-miljø med Customer Insights, bruker [Power Platform dataflyter](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) som standard. Dataflyter støtter tilkobling på stedet ved hjelp av datagatewayen. Du kan fjerne og opprette datakilder som eksisterte før et Dataverse miljø ble knyttet til, [ved å bruke lokale datagatewayer](/data-integration/gateway/service-gateway-app).

Datagatewayer fra et eksisterende Power BI- eller Power Apps-miljø vil være synlige og kan brukes på nytt i Customer Insights. Datakildesiden viser koblinger for å gå til Microsoft Power Platform-miljøet der du kan vise og konfigurere lokale datagatewayer.

> [!IMPORTANT]
> Kontroller at gatewayene er oppdatert til nyeste versjon. Du kan installere en oppdatering og konfigurere en gateway på nytt fra en ledetekst som vises på gateway-skjermen direkte, eller [laste ned den nyeste versjonen](https://powerapps.microsoft.com/downloads/). Hvis du ikke bruker den nyeste gateway-versjonen, mislykkes dataflytoppdateringen med feilmeldinger som **Nøkkelordet støttes ikke: konfigurasjonsegenskaper. Parameternavn: nøkkelord**.

## <a name="edit-power-query-data-sources"></a>Rediger Power Query-datakilder

> [!NOTE]
> Det kan hende at det ikke er mulig å gjøre endringer i datakilder som for øyeblikket brukes i en av appenes prosesser (*segmentering*, *samsvar* eller *sammenslåing*, for eksempel).
>
> Ved å bruke siden **Innstillinger** kan du spore fremdriften for hver av de aktive prosessene. Når en prosess er fullført, kan du gå tilbake til siden **Datakilder** og utføre endringene.

1. Gå til **Data** > **Datakilder**.

1. Ved siden av datakilde du vil oppdatere, velger du **Rediger**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Bruk endringene og transformasjonene i dialogboksen **Power Query - Rediger spørringer** som beskrevet under [Opprette en ny datakilde](#create-a-new-data-source).

1. Velg **Lagre** i Power Query etter at redigeringene er fullført, for å lagre endringene.
