---
title: Tjenestegrenser i Dynamics 365 Customer Insights
description: Forstå grenser og begrensninger.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791993"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Tjenestegrenser i Customer Insights-funksjoner

Denne artikkelen beskriver de innebygde grensene i Customer Insights-tjenesten, som er utformet for å sikre påliteligheten og stabiliteten til tjenesten. Eventuelle forespørsler om endringer kan utføres via [ideforumet](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Målgruppeinnsikt

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Tjenestegrenser i funksjonen for målgruppeinnsikt i Dynamics 365 Customer Insights

| Areal  | Grenser  | Notater |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenter, mål og prediksjoner | 300  | Det totale antallet [segmenter](audience-insights/segments.md), [mål](audience-insights/measures.md) og [prognoser](audience-insights/predictions.md) til sammen kan ikke overskride 300.  |
| Relasjoner | 20 dybdenivåer på relasjoner i enhetsbaner. | Når du oppretter [segmenter](audience-insights/segments.md) eller [mål](audience-insights/measures.md) ved hjelp av byggergrensesnittet, kan enhetsbaner ha opptil 20 relasjonshopp mellom startenheten og målenheten.  |


## <a name="engagement-insights"></a>Engasjementsinnsikt

### <a name="workspace-and-event-quotas"></a>Arbeidsområde- og hendelseskvoter

Engasjementsinnsikt er et svært skalerbart program som kan støtte millioner av hendelser per sekund. I offentlige forhåndsversjoner har hendelser en volumterskel. Det er også en grense på antall arbeidsområder i en organisasjon.

### <a name="engagement-insights-limits"></a>Grenser for engasjementsinnsikt

- Maksimalt hendelsesvolum per arbeidsområde = 100 hendelser per sekund

- Maksimalt antall arbeidsområder per organisasjon = 100

Når hendelser overskrider terskelen, kan det føre til tap av data i rapporter basert på disse hendelsene. Du kan [kontakte kundestøtte](https://go.microsoft.com/fwlink/?linkid=2145734) for å be om en volumøkning før du overskrider grensene. Vi samarbeider med deg for å fastslå behovet for en volumøkning og støtte forespørselen din.


[!INCLUDE[footer-include](includes/footer-banner.md)]
