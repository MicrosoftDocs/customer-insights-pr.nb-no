---
title: Aktiver bruksklare profilrapporter
description: Slik oppretter du bruksklare profilrapporter gruppert etter kjønn, alder og fylke eller opprinnelsesområde.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033964"
---
# <a name="out-of-box-profile-reports"></a>Bruksklare profilrapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En rapport er en samling datavisualiseringer for å hjelpe deg med å forstå hvordan kundene opptrer. Ved å koble til Customer Insights-målgruppeinnsikt kan engasjementsinnsikt vise en rapport med informasjon om enhetlige kundeprofiler. Denne rapporten omfatter antall profiler du har, gruppert etter kjønn, alder og geografisk plassering.

## <a name="prerequisites"></a>Forutsetninger

Miljøet for målgruppeinnsikt må lagre data i en kundestyrt Azure Data Lake Storage-konto.

Hvis du bruker en prøveversjon av målgruppeinnsikt eller et miljø i et Customer Insights-administrert datasjø, kan du [kontakte oss](https://go.microsoft.com/fwlink/?linkid=2145734) for å få hjelp.  


## <a name="enable-the-customer-profile-report"></a>Aktiver kundeprofilrapporten

En miljøadministrator må [opprette en tilkobling til målgruppeinnsikt](configure-connections.md).

Når administratoren har angitt tilkoblingsdetaljene, kan vedkommende gi tilgang til andre personer i organisasjonen for å se rapporten. Miljøadministratoren som konfigurerer tilkoblingen, har automatisk tilgang til rapporten. 

Når tilkoblingen er fullført, blir **Profiler**-funksjonen tilgjengelig i den venstre navigasjonsruten. 

- Gå til **Oppdag** > **Profiler** for å se rapporten.

**Profiler**-rapporten inneholder visualiseringer om kjønn, alder og geografisk plassering for de tilkoblede kundeprofilene.

:::image type="content" source="media/customer-profiles.png" alt-text="Kundeprofilrapport.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]