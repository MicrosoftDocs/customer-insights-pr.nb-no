---
title: Power BI-kobling
description: Finn ut hvordan du bruker Dynamics 365 Customer Insights-koblingen i Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647157"
---
# <a name="connector-for-power-bi-preview"></a>Kobling for Power BI (forhåndsvisning)

Opprett visualiseringer for dataene med Power BI Desktop. Generer ekstra innsikter og bygg rapporter med enhetlige kundedata.

## <a name="prerequisites"></a>Forutsetninger

- Du har enhetlige kundeprofiler.
- Den nyeste versjonen av [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) er installert på datamaskinen. [Lær mer om Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurer koblingen for Power BI

1. I Power BI Desktop velger du **Fil** > **Hent data**.

1. Velg **Se mer** og søk etter **Dynamics 365 Customer Insights**

1. Velg **Koble til**.

1. **Logg på** med samme organisasjonskonto som du bruker for Customer Insights, og velg **Koble til**.
   > [!NOTE]
   > Kontoen du angir i dette trinnet, brukes til å hente data fra Customer Insights og trenger ikke være den samme som du er logget på Power BI. Hvis du vil tilbakestille kontoen som brukes til datainnhenting, åpner du Power BI og går til **Fil** > **Alternativer** > **Instillinger** > **Datakildeinnstillinger**. I listen over datakilder velger du **Dynamics 365 Customer Insights-pålogging** og deretter **Fjern tillatelser**.  

1. I **Navigator**-dialogboksen. Du ser listen over alle miljøer som du har tilgang til. Utvid et miljø, og åpne en av mappene (enheter, mål, segmenter, suppleringer). Åpne for eksempel **Enheter**-mappen for å se alle enhetene du kan importere.

   ![Power BI-koblingsnavigator.](media/power-bi-navigator.png "Power BI-koblingsnavigator")

1. Merk av i avmerkingsboksene ved siden av enhetene som skal inkluderes, og velg **Last inn**. Du kan velge flere enheter fra flere miljøer.

1. Det vises en dialogboks for innlasting når enhetene lastes inn. Når alle de valgte enhetene er lastet, kan du bruke funksjonene i Power BI til å visualisere dataene.

## <a name="large-data-sets"></a>Store datasett

Customer Insights-koblingen for Power BI er utformet for å fungere for datasett som inneholder opptil 1 000 000 kundeprofiler. Det kan hende at importen av større datasett fungerer, men det krever lang tid. Prosessen kan også bli tidsavbrutt på grunn av Power BI-begrensninger. Hvis du vil ha mer informasjon, kan du se [Power BI: Anbefalinger for store datasett](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Arbeide med et delsett av data

Vurder å arbeide med et delsett av dataene. Du kan for eksempel opprette [segmenter](segments.md) i stedet for å eksportere alle kundeoppføringer til Power BI.

## <a name="troubleshooting"></a>Feilsøking

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights-miljøet vises ikke i Power BI

Miljøer der mer enn én [relasjon](relationships.md) er definert mellom to identiske enheter i Customer Insights, er ikke tilgjengelige i Power BI-koblingen.

Du kan identifisere og fjerne de dupliserte relasjonene.

1. Gå til **Data** > **Relasjoner** i miljøet du mangler i Power BI.
2. Identifiser dupliserte relasjoner:
   - Kontroller om mer enn én relasjon er definert mellom de samme to entitetene.
   - Kontroller om det er en relasjon som er opprettet mellom to entiteter som begge er inkludert i foreningsprosessen. Det er en implisitt relasjon definert mellom alle enheter som er inkludert i foreningsprosessen.
3. Fjern eventuelle dupliserte relasjoner som er identifisert.

Når du har fjernet dupliserte relasjoner, kan du prøve å konfigurere Power BI-koblingen på nytt. Miljøet skal være tilgjengelig nå.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Feil i datofelter under innlasting av enheter i Power BI Desktop

Når du laster inn enheter som inneholder felter med datoformat som MM/DD/ÅÅÅÅ, kan det oppstå feil på grunn av formater for nasjonale innstillinger som ikke samsvarer. Dette samsvaret skjer når Power BI Desktop-filen er satt til en annen nasjonal fil enn Engelsk (USA) fordi datofelter i Customer Insights lagres i amerikansk format.

Filen Power BI Desktop har én innstilling for nasjonale innstillinger, som brukes ved henting av data. Hent disse datofeltene tolkes riktig, og angi de nasjonale innstillingene for .BPI-filen til engelsk (USA). [Finn ut hvordan du endrer de nasjonale innstillingene for en Power BI Desktop-fil](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]