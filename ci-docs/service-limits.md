---
title: Tjenestegrenser i Customer Insights
description: Forstå grenser og begrensninger i Customer Insights SaaS-tjenesten.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940680"
---
# <a name="service-limits-in-customer-insights"></a>Tjenestegrenser i Customer Insights

Denne artikkelen beskriver de innebygde grensene i Customer Insights-tjenesten, som er utformet for å sikre påliteligheten og stabiliteten til tjenesten. Eventuelle forespørsler om endringer kan utføres via [ideforumet](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Areal  | Grenser  | Notater |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenter, mål og prediksjoner | 300  | Det totale antallet [segmenter](segments.md), [mål](measures.md) og [prognoser](predictions.md) til sammen kan ikke overskride 300.  |
| Relasjoner | 20 dybdenivåer på relasjoner i enhetsbaner. | Når du oppretter [segmenter](segments.md) eller [mål](measures.md) ved hjelp av byggergrensesnittet, kan enhetsbaner ha opptil 20 relasjonshopp mellom startenheten og målenheten.  |

## <a name="fair-scheduling-of-jobs"></a>Rettferdig planlegging av jobber

Customer Insights er en SaaS-tjeneste som bruker delte Azure-ressurser. Kunder har en tendens til å ha arbeidsbelastninger med variabel intensitet og ulike tidsplaner. For å sikre rettferdig tilgang til de underliggende ressursene sørger vi for at systemprosessene utføres i en rettferdig rekkefølge. Eksempler på systemprosesser er jobber relatert til datasamling, segmentoppdateringer eller målingsberegning. Den rettferdige planleggingen beskytter deg mot kø for ressurser hvis det er en topp i forespurte jobber. Samtidig garanterer ikke Customer Insights at alle jobbene du setter i kø, behandles parallelt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
