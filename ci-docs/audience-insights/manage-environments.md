---
title: Opprette og behandle miljøer
description: Lær hvordan du registrerer deg for tjenesten og hvordan du administrerer miljøer.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 06310ea6fc72f26e21e185a6abcb5d19d4b201f6
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259111"
---
# <a name="manage-environments"></a>Behandle miljøer

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Denne artikkelen forklarer hvordan du oppretter en ny organisasjon og hvordan du klargjør et miljø.

## <a name="sign-up-and-create-an-organization"></a>Registrere og opprette en organisasjon

1. Gå til [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/)-nettsted.

2. Velg **Komme i gang**.

3. Velg ønsket registreringsscenario, og velg den tilsvarende koblingen.

4. Godta vilkårene, og velg **Fortsett** for å starte opprettingen av organisasjonen.

5. Når du har opprettet miljøet, blir du omdirigert til [Customer Insights](https://home.ci.ai.dynamics.com).

6. Bruk demonstrasjonsmiljøet til å utforske appen, eller opprett et nytt miljø ved å følge fremgangsmåten i neste del.

7. Etter at du har angitt miljøinnstillingene, velger du **Opprett**.

8. Du blir logget på etter at miljøet er opprettet.

## <a name="create-an-environment-in-an-existing-organization"></a>Opprette et miljø i en eksisterende organisasjon

Du kan opprette et nytt miljø på to måter. Du kan enten spesifisere en helt ny konfigurasjon, eller du kan kopiere noen konfigurasjonsinnstillinger fra et eksisterende miljø.

> [!NOTE]
> Organisasjoner kan opprette *to* miljøer for hver Customer Insights-lisens. Hvis organisasjonen din kjøper flere enn én lisens, kan du [kontakte kundestøtteteamet](https://go.microsoft.com/fwlink/?linkid=2079641) for å øke antallet tilgjengelige miljøer. Hvis du vil ha mer informasjon om kapasitet og tilleggskapasitet, kan du laste ned [lisensieringsveiledning for Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Slik oppretter du et miljø:

1. Velg **Miljø**-velgeren i overskriften i appen.

1. Velg **Ny**.

   > [!div class="mx-imgBorder"]
   > ![Miljøinnstillinger](media/environment-settings-dialog.png)

1. I dialogboksen **Opprett nytt miljø** velger du **Nytt miljø**.

   Hvis du vil [kopiere data fra det gjeldende miljøet](#considerations-for-copy-configuration-preview), velger du **Kopier fra eksisterende miljø**. Det vises en liste over alle tilgjengelige miljøer i organisasjonen, der du kan kopiere data fra.

1. Angi følgende detaljer:
   - **Navn**: Navnet på dette miljøet. Dette feltet er allerede fylt ut hvis du har kopiert et eksisterende miljø, men du kan endre det.
   - **Område**: Området som servicen er distribuert i, og driftet.
   - **Type**: Velg om du vil opprette et produksjons- eller sandkassemiljø.

1. Du kan eventuelt velge **Avanserte innstillinger**:

   - **Lagre alle data i**: Angir hvor du vil lagre utdataene som er generert av Customer Insights. Du har to alternativer: **Customer Insights-lagring** (en Azure Data Lake administrert av Customer Insights-teamet) og **Azure Data Lake Storage Gen2** (din egen Azure Data Lake Storage). Som standard er det merket av for lagringsalternativet Customer Insights.

   > [!NOTE]
   > Når du lagrer data i Azure Data Lake Storage, godtar du at dataene overføres til og lagres i den riktige geografiske plasseringen for denne Azure Storage-kontoen, som kan variere fra der dataene lagres i Dynamics 365 Customer Insights. [Finn ut mer om Microsofts klareringssenter.](https://www.microsoft.com/trust-center)
   >
   > For øyeblikket lagres enheter alltid i den Customer Insights-administrerte datasjøen.
   > Vi støtter bare Azure Data Lake Gen2-lagringskontoer fra det samme Azure-området du valgte da du opprettet miljøet.
   > Vi støtter bare Azure Data Lake Gen2 Hierarkisk navneområde (HNS)-aktiverte lagringskontoer.

   - For Azure Data Lake Storage Gen2 kan du velge mellom et ressursbasert alternativ og et abonnementsbasert alternativ for godkjenning. Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md). **Beholder**-navnet kan ikke endres og er `customerinsights`.
   
   - Hvis du vil bruke [prediksjoner](predictions.md), konfigurere datadeling med Microsoft Dataverse, eller aktivere datainntak fra lokale datakilder, oppgir du nettadressen for Microsoft Dataverse-miljøet under **Konfigurer datadeling med Microsoft Dataverse og aktiver flere funksjoner**. Velg **Aktiver datadeling** for å dele Customer Insights-utdata med en Microsoft Dataverse-administrert datasjø.

     > [!NOTE]
     > - Det er for øyeblikket ikke støtte for datadeling med Microsoft Dataverse-styrt datasjø når du lagrer alle dataene i din egen Azure Data Lake Storage.
     > - [Prediksjon av manglende miljøer i en enhet](predictions.md) støttes for øyeblikket ikke når du aktiverer datadeling med Microsoft Dataverse-administrert datasjø.

     > [!div class="mx-imgBorder"]
     > ![Konfigurasjonsalternativer for å aktivere datadeling med Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)

   Når du kjører prosesser, for eksempel datainntak eller segmentopprettelse, blir tilsvarende mapper opprettet i lagringskontoen du angav ovenfor. Datafiler og model.json-filer blir opprettet og lagt til i mapper basert på prosessnavnet.

   Hvis du oppretter flere miljøer i Customer Insights og velger å lagre enhetene fra disse miljøene i lagringskontoen, blir det opprettet separate mapper for hvert miljø med ci_<environmentid> i beholderen.

### <a name="considerations-for-copy-configuration-preview"></a>Vurderinger ved kopieringskonfigurasjon (forhåndsvisning)

Følgende konfigurasjonsinnstillinger kopieres:

- Funksjonskonfigurasjoner
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

Følgende innstillinger kopieres *ikke*:

- Kundeprofiler.
- Legitimasjon for datakilde. Du må angi legitimasjonen for hver datakilde og oppdatere datakildene manuelt.
- Datakilder fra Common Data Model-mappe og Common Data Service-administrert sjø. Du må opprette disse datakildene manuelt med samme navn som i kildemiljøet.

Når du kopierer et miljø, vises en bekreftelsesmelding om at det nye miljøet er opprettet. Velg **Gå til datakilder** for å vise listen over datakilder.

Alle datakildene vil vise statusen **Legitimasjon kreves**. Rediger datakildene, og angi legitimasjonen for å oppdatere dem.

> [!div class="mx-imgBorder"]
> ![Kopierte datakilder](media/data-sources-copied.png)

Etter at du har oppdatert datakildene, går du til **Data** > **Samle**. Her finner du innstillinger fra kildemiljøet. Rediger dem etter behov, eller velg **Kjør** for å starte prosessen med datasamling og opprette den enhetlige kundeenheten.

Når datasamlingen er fullført, kan du gå til **Mål** og **Segmenter** for å oppdatere dem også.

## <a name="edit-an-existing-environment"></a>Redigere et eksisterende miljø

Du kan redigere noen av detaljene i eksisterende miljøer.

1.  Velg **Miljø**-velgeren i overskriften i appen.

2.  Velg **Rediger**-ikonet.

3. I **Rediger miljø**-boksen kan du oppdatere miljøets **visningsnavn**, men du kan ikke endre **område** eller **type**.

4. Hvis et miljø er konfigurert til å lagre data i Azure Data Lake Storage Gen2, kan du oppdatere **kontonøkkelen**. Du kan imidlertid ikke endre **Kontonavn** eller **Beholder**-navn.

5. Du kan eventuelt oppdatere fra en tilkobling basert på en kontonøkkel til en ressursbasert eller abonnementsbasert tilkobling. Når du har oppgradert, kan du ikke tilbakestille til kontonøkkelen etter oppdateringen. Hvis du vil ha mer informasjon, kan du se [Koble til målgruppeinnsikt i en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekontohaver](connect-service-principal.md). Du kan ikke endre informasjon om en **beholder** når du oppdaterer tilkoblingen.

6. Alternativt kan du angi en URL-adresse for Microsoft Dataverse-miljøet under **Konfigurere datadeling med Microsoft Dataverse og aktivere flere funksjoner**. Disse funksjonene omfatter datadeling med programmer og løsninger basert på Microsoft Dataverse, datainntak fra lokale datakilder eller bruk av [prediksjoner](predictions.md). Velg **Aktiver datadeling** for å dele Customer Insights-utdata med en Microsoft Dataverse-administrert Data Lake.

   > [!NOTE]
   > - Det er for øyeblikket ikke støtte for datadeling med Microsoft Dataverse-styrt datasjø når du lagrer alle dataene i din egen Azure Data Lake Storage.
   > - [Prediksjon av manglende verdier i en enhet](predictions.md) støttes for øyeblikket ikke når du aktiverer datadeling med Microsoft Dataverse-administrert Data Lake.

   Etter at du har aktivert datadeling med Microsoft Dataverse, starter en fullstendig oppdatering av datakildene og andre prosesser. Hvis prosesser kjører, vises ikke alternativet for å aktivere datadeling med Microsoft Dataverse. Vent til disse prosessene er fullført eller avbrutt for å aktivere datadeling. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigurasjonsalternativer for å aktivere datadeling med Microsoft Dataverse.":::
   
   Når du kjører prosesser, for eksempel datainntak eller segmentopprettelse, blir tilsvarende mapper opprettet i lagringskontoen du angav ovenfor. Datafiler og model.json-filer blir opprettet og lagt til i de respektive undermappene, avhengig av prosessen du kjører.

## <a name="reset-an-existing-environment"></a>Tilbakestille et eksisterende miljø

Som en administrator kan du tilbakestille et miljø til en tom tilstand hvis du vil slette alle konfigurasjoner og fjerne data som er hentet inn.

1.  Velg **Miljø**-velgeren i overskriften i appen. 

2.  Velg miljøet du vil tilbakestille, og velg ellipsen **...**. 

3. Velg **Tilbakestill**-alternativet. 

4.  Bekreft slettingen ved å skrive inn miljønavnet og velge **Tilbakestill**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Slett et eksisterende miljø (tilgjengelig bare for administratorer)

Som en administrator kan du slette et miljø du administrerer.

1.  Velg **Miljø**-velgeren i overskriften i appen.

2.  Velg miljøet du vil tilbakestille, og velg ellipsen **...**. 

3. Velg **Slett**-alternativet. 

4.  Bekreft slettingen ved å angi miljønavnet og velge **Slett**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
