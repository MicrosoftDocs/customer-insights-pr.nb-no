---
title: Opprette og behandle miljøer
description: Lær hvordan du registrerer deg for tjenesten og hvordan du administrerer miljøer.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034189"
---
# <a name="manage-environments"></a>Behandle miljøer

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Bytt miljøer

Velg kontrollen **Miljø** øverst i høyre hjørne på siden for å endre miljøer.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Skjermbilde av kontrollen for å bytte miljø.":::

Administratorer kan [opprette](get-started-paid.md) og behandle miljøer.

## <a name="edit-an-existing-environment"></a>Redigere et eksisterende miljø

Du kan redigere noen av detaljene i eksisterende miljøer.

1.  Velg **Miljø**-velgeren i overskriften i appen.

2.  Velg **Rediger**-ikonet.

3. I **Rediger miljø**-boksen kan du oppdatere miljøets **visningsnavn**, men du kan ikke endre **område** eller **type**.

4. Hvis et miljø er konfigurert til å lagre data i Azure Data Lake Storage, kan du oppdatere **Nøkkel for forretningsforbindelse**. Du kan imidlertid ikke endre **Kontonavn** eller **Beholder**-navn.

5. Du kan eventuelt oppdatere fra en tilkobling basert på en kontonøkkel til en ressursbasert eller abonnementsbasert tilkobling. Når du har oppgradert, kan du ikke tilbakestille til kontonøkkelen etter oppdateringen. Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md). Du kan ikke endre informasjon om en **beholder** når du oppdaterer tilkoblingen.

6. Alternativt kan du angi en URL-adresse for Microsoft Dataverse-miljøet under **Konfigurere datadeling med Microsoft Dataverse og aktivere flere funksjoner**. Disse funksjonene omfatter datadeling med programmer og løsninger basert på Microsoft Dataverse, datainntak fra lokale datakilder eller bruk av [prediksjoner](predictions.md). Velg **Aktiver datadeling** for å dele Customer Insights-utdata med en Microsoft Dataverse-administrert Data Lake.

   > [!NOTE]
   > - Det er for øyeblikket ikke støtte for datadeling med Microsoft Dataverse-styrt datasjø når du lagrer alle dataene i din egen Azure Data Lake Storage.
   > - [Prediksjon for manglende verdier i en enhet](predictions.md) og PowerBI Embedded-rapporter i målgruppeinnsikt (hvis aktivert i miljøet) støttes for øyeblikket ikke når du aktiverer deling av data med administrert Microsoft Dataverse-datasjø.

   Etter at du har aktivert datadeling med Microsoft Dataverse, starter en fullstendig oppdatering av datakildene og andre prosesser. Hvis prosesser kjører, vises ikke alternativet for å aktivere datadeling med Microsoft Dataverse. Vent til disse prosessene er fullført eller avbrutt for å aktivere datadeling. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigurasjonsalternativer for å aktivere datadeling med Microsoft Dataverse.":::
   
   Når du kjører prosesser, for eksempel datainntak eller segmentopprettelse, blir tilsvarende mapper opprettet i lagringskontoen du angav ovenfor. Datafiler og model.json-filer blir opprettet og lagt til i de respektive undermappene, avhengig av prosessen du kjører.

## <a name="copy-the-environment-configuration"></a>Kopier miljøkonfigurasjonen

Når du oppretter et nytt miljø, kan du velge å kopiere konfigurasjonen fra et eksisterende miljø. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skjermbilde av innstillingsalternativene i miljøinnstillingene.":::

Det vises en liste over alle tilgjengelige miljøer i organisasjonen, der du kan kopiere data fra.

Følgende konfigurasjonsinnstillinger kopieres:

- Samlede/importerte datakilder
- Konfigurasjon av forening av data (tilordning, samsvar, sammenslåing)
- Segmenter
- Mål
- Relasjoner
- Aktiviteter
- Søk- og filterindeks
- Eksportmål
- Planlagt oppdatering
- Suppleringer
- Modelladministrasjon
- Rolletildelinger

Følgende data er *ikke* kopiert:

- Kundeprofiler.
- Legitimasjon for datakilde. Du må angi legitimasjonen for hver datakilde og oppdatere datakildene manuelt.
- Datakilder fra mappen Common Data Model og Dataverse-administrerte Data Lake. Du må opprette disse datakildene manuelt med samme navn som i kildemiljøet.

Når du kopierer et miljø, vises en bekreftelsesmelding om at det nye miljøet er opprettet. Velg **Gå til datakilder** for å vise listen over datakilder.

Alle datakildene vil vise statusen **Legitimasjon kreves**. Rediger datakildene, og angi legitimasjonen for å oppdatere dem.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste over datakilder som ble kopiert og trenger godkjenning.":::

Etter at du har oppdatert datakildene, går du til **Data** > **Samle**. Her finner du innstillinger fra kildemiljøet. Rediger dem etter behov, eller velg **Kjør** for å starte prosessen med datasamling og opprette den enhetlige kundeenheten.

Når datasamlingen er fullført, kan du gå til **Mål** og **Segmenter** for å oppdatere dem også.

## <a name="reset-an-existing-environment"></a>Tilbakestille et eksisterende miljø

Som en administrator kan du tilbakestille et miljø til en tom tilstand hvis du vil slette alle konfigurasjoner og fjerne data som er hentet inn.

1.  Velg **Miljø**-velgeren i overskriften i appen. 

2.  Velg miljøet du vil tilbakestille, og velg ellipsen (**...**). 

3. Velg **Tilbakestill**-alternativet. 

4.  Bekreft slettingen ved å skrive inn miljønavnet og velge **Tilbakestill**.

## <a name="delete-an-existing-environment"></a>Slette et eksisterende miljø

Som en administrator kan du slette et miljø du administrerer.

1.  Velg **Miljø**-velgeren i overskriften i appen.

2.  Velg miljøet du vil tilbakestille, og velg ellipsen (**...**). 

3. Velg **Slett**-alternativet. 

4.  Bekreft slettingen ved å angi miljønavnet og velge **Slett**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
