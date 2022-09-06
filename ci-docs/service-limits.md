---
title: Tjenestegrenser i Customer Insights
description: Forstå grenser og begrensninger i Customer Insights SaaS-tjenesten.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 421e1aa41a54a4b8c34ac27fc7c02e510d2bb588
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387168"
---
# <a name="service-limits-in-customer-insights"></a>Tjenestegrenser i Customer Insights

 Customer Insights har innebygde begrensninger som er utformet for å sikre påliteligheten og stabiliteten til tjenesten. Eventuelle forespørsler om endringer kan utføres via [ideforumet](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Areal  | Grenser  | Notater |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenter, mål og prediksjoner | 300  | Det totale antallet [segmenter](segments.md), [mål](measures.md) og [prognoser](predictions.md) til sammen kan ikke overskride 300.  |
| Relasjoner | 20 dybdenivåer på relasjoner i enhetsbaner. | Når du oppretter [segmenter](segments.md) eller [mål](measures.md) ved hjelp av byggergrensesnittet, kan enhetsbaner ha opptil 20 relasjonshopp mellom startenheten og målenheten.  |

## <a name="fair-scheduling-of-jobs"></a>Rettferdig planlegging av jobber

Customer Insights er en SaaS-tjeneste som bruker delte Azure-ressurser. Kunder har en tendens til å ha arbeidsbelastninger med variabel intensitet og ulike tidsplaner. For å sikre rettferdig tilgang til de underliggende ressursene sørger vi for at systemprosessene utføres i en rettferdig rekkefølge. Eksempler på systemprosesser er jobber relatert til datasamling, segmentoppdateringer eller målingsberegning. Den rettferdige planleggingen beskytter deg mot kø for ressurser hvis det er en topp i forespurte jobber. Samtidig garanterer ikke Customer Insights at alle jobbene du setter i kø, behandles parallelt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
