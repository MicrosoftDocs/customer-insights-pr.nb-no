---
title: Tjenestegrenser i Dynamics 365 Customer Insights
description: Forstå grenser og begrensninger.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641774"
---
# <a name="service-limits-in-customer-insights"></a>Tjenestegrenser i Customer Insights

Denne artikkelen beskriver de innebygde grensene i Customer Insights-tjenesten, som er utformet for å sikre påliteligheten og stabiliteten til tjenesten. Eventuelle forespørsler om endringer kan utføres via [ideforumet](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Areal  | Grenser  | Notater |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenter, mål og prediksjoner | 300  | Det totale antallet [segmenter](segments.md), [mål](measures.md) og [prognoser](predictions.md) til sammen kan ikke overskride 300.  |
| Relasjoner | 20 dybdenivåer på relasjoner i enhetsbaner. | Når du oppretter [segmenter](segments.md) eller [mål](measures.md) ved hjelp av byggergrensesnittet, kan enhetsbaner ha opptil 20 relasjonshopp mellom startenheten og målenheten.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
