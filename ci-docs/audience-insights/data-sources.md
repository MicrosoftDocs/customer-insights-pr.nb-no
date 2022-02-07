---
title: Bruke datakildene til å ta inn data
description: Lær hvordan du importerer data fra ulike kilder.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
---

# <a name="data-sources-overview"></a>Oversikt over datakilder



Funksjonen for målgruppeinnsikt i Dynamics 365 Customer Insights kobler til data fra et bredt sett med kilder. Tilkobling til en datakilde kalles ofte *datainntak*. Når du har integrert dataene, kan du [samle](data-unification.md) og utføre handlinger på dataene.

## <a name="add-a-data-source"></a>Legg til en datakilde

Se de detaljerte artiklene om hvordan du legger til datakilde, avhengig av alternativet du velger.

Du kan legge til følgende datakilder:

- [Power Query-koblinger](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse-sjø](connect-dataverse-managed-lake.md)

> [!NOTE]
> Hvis du bruker prøveversjonen, inneholder importmetodedelen et alternativ for **Customer Insights-databibliotek**. Velg dette alternativet for å velge et eksempeldatasett tilgjengelig for ulike bransjer. Se [Dynamics 365 Customer Insights-prøveversjon](../trial-signup.md) hvis du vil ha mer informasjon.

## <a name="add-data-from-on-premises-data-sources"></a>Legge til data fra lokale datakilder

Inntak av data fra lokale datakilder i målgruppeinnsikt støttes basert på Microsoft Power Platform-dataflyter. Du kan aktivere dataflyter i Customer Insights ved [å angi Microsoft Dataverse URL-adressen for miljøet](create-environment.md) når du konfigurerer miljøet.

Datakilder som opprettes etter at et miljø er knyttet til et Dataverse-miljø med Customer Insights, bruker [Power Platform dataflyter](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) som standard. Dataflyter støtter tilkobling på stedet ved hjelp av datagatewayen. Du kan fjerne og opprette datakilder som eksisterte før et Dataverse miljø ble knyttet til, [ved å bruke lokale datagatewayer](/data-integration/gateway/service-gateway-app).

Datagatewayer fra et eksisterende Power BI- eller Power Apps-miljø vil være synlige og kan brukes på nytt i Customer Insights. Datakildesiden viser koblinger for å gå til Microsoft Power Platform-miljøet der du kan vise og konfigurere lokale datagatewayer.

## <a name="review-ingested-data"></a>Se gjennom integrerte data

Du ser navnet på hver integrerte datakilde, statusen og siste gang dataene ble oppdatert for kilden. Du kan sortere listen over datakilder etter hver kolonne.

> [!div class="mx-imgBorder"]
> ![Tillagt datakilde.](media/configure-data-datasource-added.png "Tillagt datakilde")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Det kan ta tid å laste inn data. Etter en vellykket oppdatering kan de innhentede dataene gjennomgås fra siden **Enheter**. Hvis du vil ha mer informasjon, se [Enheter](entities.md).

## <a name="refresh-a-data-source"></a>Oppdatere en datakilde

Datakilder kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov. 

Gå til **Administrasjon** > **System** > [**Plan**](system.md#schedule-tab) for å konfigurere planlagte oppdateringer av alle datakilder som er tatt inn.

Følg denne fremgangsmåten for å oppdatere en datakilde ved behov:

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

2. Velg den loddrette ellipsen ved siden av datakildene du vil oppdatere, og velg **Oppdater** fra rullegardinlisten.

3. Datakilden utløses nå for manuell oppdatering. Oppdatering av en datakilde vil oppdatere både enhetsskjemaet og dataene for alle enhetene som er angitt i datakilden.

4. Velg **Stopp oppdatering** hvis du vil avbryte en eksisterende oppdatering, og datakilden tilbakestilles til den siste oppdateringsstatusen.

## <a name="delete-a-data-source"></a>Slette en datakilde

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

2. Velg den loddrette ellipsen ved siden av datakildene du vil fjerne, og velg **Slett** fra rullegardinmenyen.

3. Bekreft slettingen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
