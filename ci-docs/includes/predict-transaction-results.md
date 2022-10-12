---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611107"
---
- **Ytelse for opplæringsmodell**: Graderingene A, B eller C angir ytelsen til prediksjonen og kan hjelpe deg å ta beslutningen om å bruke resultatene som er lagret i utdataenheten.

  Vurderinger fastsettes basert på følgende regler:
  - **A** Når modellen har forutsett nøyaktig minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er større enn grunnlinjen med minst 10 %.
  - **B** Når modellen har forutsett nøyaktig minst 50 % av de totale prognosene, og når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er opptil 10 %større enn grunnlinjen.
  - **C** Når modellen har forutsett nøyaktig mindre enn 50 % av de totale prognosene, eller når prosentandelen av nøyaktige prognoser for kunder som har frafalt, er mindre enn grunnlinjen.
  - **Grunnlinje** tar inndataene i tidsvinduets for prediksjonen for modellen (for eksempel ett år) og oppretter forskjellige fraksjoner av tiden ved å dele den på 2 til den når én måned eller mindre. Den bruker disse brøkene til å opprette en forretningsregel for kunder som ikke har kjøpt i denne tidsrammen. Disse kundene anses som frafalt. Den tidsbaserte forretningsregelen med høyest mulig evne til å forutse hvem som sannsynligvis vil frafalle, velges som grunnlinjemodellen.

- **Sannsynligheten for frafall (antall kunder)**: Grupper av kunder basert på den predikerte risikoen for frafall. Du kan eventuelt [opprette kundesegmenter](../prediction-based-segment.md) med høy frafallsrisiko. Slike segmenter hjelper deg med å forstå hvor grensen bør gå for segmentmedlemskap.

- **Mest innflytelsesrike faktorer**: Det er mange faktorer du må ta hensyn til når du oppretter forutsigelsen. Hver av faktorene har sin viktighet beregnet for de aggregerte prognosene som en modell oppretter. Bruk disse faktorene til å validere forutsigelsesresultatene. Eller bruk denne informasjonen senere til å [opprette segmenter](../prediction-based-segment.md) som kan ha innvirkning på frafallsrisiko for kunder.