---
title: Power BI-kobling
description: Finn ut hvordan du bruker Dynamics 365 Customer Insights-koblingen i Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406496"
---
# <a name="connector-for-power-bi-preview"></a>Kobling for Power BI (forhåndsvisning)

Opprett visualiseringer for dataene med Power BI Desktop. Generer ekstra innsikter og bygg rapporter med enhetlige kundedata.

## <a name="prerequisites"></a>Forutsetninger

- Du har enhetlige kundeprofiler.
- Den nyeste versjonen av [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) er installert på datamaskinen. [Lær mer om Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurer koblingen for Power BI

1. I Power BI Desktop velger du **Fil** > **Hent data**.

1. Velg **Se mer** og søk etter **Dynamics 365 Customer Insights**

1. Velg resultatet, og velg **Koble til**.

1. **Logg på** med samme organisasjonskonto som du bruker for Customer Insights, og velg **Koble til**.
   > [!NOTE]
   > Kontoen du angir i dette trinnet, brukes til å hente data fra Customer Insights og trenger ikke være den samme som du er logget på Power BI. Hvis du vil tilbakestille kontoen som brukes til datainnhenting, åpner du Power BI og går til **Fil** > **Alternativer** > **Instillinger** > **Datakildeinnstillinger**. I listen over datakilder velger du **Dynamics 365 Customer Insights-pålogging** og deretter **Fjern tillatelser**.  

1. I **Navigator**-dialogboksen. Du ser listen over alle miljøer som du har tilgang til. Utvid et miljø, og åpne en av mappene (enheter, mål, segmenter, suppleringer). Åpne for eksempel **Enheter**-mappen for å se alle enhetene du kan importere.

   ![Power BI-koblingsnavigator](media/power-bi-navigator.png "Power BI-koblingsnavigator")

1. Merk av i avmerkingsboksene ved siden av enhetene som skal inkluderes, og velg **Last inn**. Du kan velge flere enheter fra flere miljøer.

1. Det vises en dialogboks for innlasting når enhetene lastes inn. Når alle de valgte enhetene er lastet, kan du bruke funksjonene i Power BI til å visualisere dataene.

## <a name="large-data-sets"></a>Store datasett

Customer Insights-koblingen for Power BI er utformet for å fungere for datasett som inneholder opptil 1 000 000 kundeprofiler. Det kan hende at importen av større datasett fungerer, men det krever lang tid. Prosessen kan også bli tidsavbrutt på grunn av Power BI-begrensninger. Hvis du vil ha mer informasjon, kan du se [Power BI: Anbefalinger for store datasett](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Arbeide med et delsett av data

Vurder å arbeide med et delsett av dataene. Du kan for eksempel opprette [segmenter](segments.md) i stedet for å eksportere alle kundeoppføringer til Power BI.