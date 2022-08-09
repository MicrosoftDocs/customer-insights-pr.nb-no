---
title: Power BI-kobling (forhåndsvisning)
description: Finn ut hvordan du bruker Dynamics 365 Customer Insights-koblingen i Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196682"
---
# <a name="power-bi-connector-preview"></a>Power BI-kobling (forhåndsvisning)

Opprett visualiseringer for dataene med Microsoft Power BI Desktop. Generer ekstra innsikter og bygg rapporter med enhetlige kundedata.

## <a name="prerequisites"></a>Forutsetning

- Enhetlige kundeprofiler.
- Den nyeste versjonen av [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) er installert på datamaskinen. [Lær mer om Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurer koblingen for Power BI

1. I Power BI Desktop velger du **Fil** > **Hent data**.

1. Velg **Se mer** og søk etter **Dynamics 365 Customer Insights**

1. Velg **Koble til**.

1. **Logg på** med samme organisasjonskonto som du bruker for Customer Insights, og velg **Koble til**.
   > [!NOTE]
   > Kontoen du angir i dette trinnet, brukes til å hente data fra Customer Insights og trenger ikke være den samme som du er logget på Power BI. Hvis du vil tilbakestille kontoen som brukes til datainnhenting, åpner du Power BI og går til **Fil** > **Alternativer** > **Instillinger** > **Datakildeinnstillinger**. I listen over datakilder velger du **Dynamics 365 Customer Insights-pålogging** og deretter **Fjern tillatelser**.  

1. I dialogboksen **Navigator** viser du listen over alle miljøer du har tilgang til. Utvid et miljø, og åpne en av mappene (enheter, mål, segmenter, suppleringer). Åpne for eksempel **Enheter**-mappen for å se alle enhetene du kan importere.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Power BI-koblingsnavigator.":::

1. Merk av i avmerkingsboksene ved siden av enhetene som skal inkluderes, og velg **Last inn**. Du kan velge flere enheter fra flere miljøer.

   En dialogboks for innlasting vises mens enhetene lastes inn. Når alle de valgte enhetene er lastet inn, bruker du funksjonene i Power BI til å visualisere dataene.

## <a name="large-data-sets"></a>Store datasett

Customer Insights-koblingen for Power BI er utformet for å fungere for datasett som inneholder opptil 1 000 000 kundeprofiler. Du kan kanskje importere større datasett, men det tar lang tid og kan bli tidsavbrutt på grunn av begrensninger i Power BI. Hvis du vil ha mer informasjon, kan du se [Power BI: Anbefalinger for store datasett](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Arbeide med et delsett av data

Vurder å arbeide med et delsett av dataene. Opprett for eksempel [segmenter](segments.md) i stedet for å eksportere alle kundeoppføringer til Power BI.

## <a name="troubleshooting"></a>Feilsøking

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights-miljøet vises ikke i Power BI

Miljøer der mer enn én [relasjon](relationships.md) er definert mellom to identiske enheter i Customer Insights, er ikke tilgjengelige i Power BI-koblingen.

Identifiser og fjern de dupliserte relasjonene.

1. Gå til **Data** > **Relasjoner** i miljøet du mangler i Power BI.
1. Identifiser dupliserte relasjoner:
   - Kontroller om mer enn én relasjon er definert mellom de samme to entitetene.
   - Kontroller om det er en relasjon som er opprettet mellom to entiteter som begge er inkludert i foreningsprosessen. Det er en implisitt relasjon definert mellom alle enheter som er inkludert i foreningsprosessen.
1. Fjern eventuelle dupliserte relasjoner som er identifisert.

Når du har fjernet dupliserte relasjoner, kan du prøve å konfigurere Power BI-koblingen på nytt.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Feil i datofelter under innlasting av enheter i Power BI Desktop

Når du laster inn enheter som inneholder felter med datoformat som MM/DD/ÅÅÅÅ, kan det oppstå feil på grunn av formater for nasjonale innstillinger som ikke samsvarer. Dette samsvaret skjer når Power BI Desktop-filen er satt til en annen nasjonal fil enn Engelsk (USA) fordi datofelter i Customer Insights lagres i amerikansk format.

Filen Power BI Desktop har én innstilling for nasjonale innstillinger, som brukes ved henting av data. Du kan rette datofeilene ved å [sette de nasjonale innstillingene for .BPI-filen](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) til Engelsk (USA).

[!INCLUDE [footer-include](includes/footer-banner.md)]
