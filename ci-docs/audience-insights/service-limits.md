---
title: Tjenestegrenser
description: Forstå grenser og begrensninger.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034876"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Tjenestegrenser i funksjonen for målgruppeinnsikt i Dynamics 365 Customer Insights

Denne artikkelen beskriver de innebygde grensene i Customer Insights-tjenesten, som er utformet for å sikre påliteligheten og stabiliteten til tjenesten. Eventuelle forespørsler om endringer kan utføres via [ideforumet](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Område  | Grenser  | Merknader |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenter og mål | 100 segmenter eller mål. | Det totale antallet aktive [segmenter](segments.md) og [mål](measures.md) kombinert kan ikke overskride 100.  |
| Relasjoner | 20 dybdenivåer på relasjoner i enhetsbaner. | Når du oppretter [segmenter](segments.md) eller [mål](measures.md) ved hjelp av byggergrensesnittet, kan enhetsbaner ha opptil 20 relasjonshopp mellom startenheten og målenheten.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]