---
title: Opprette og behandle miljøer
description: Lær hvordan du registrerer deg for tjenesten og hvordan du administrerer miljøer.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 309b2a900e50727ffa655fc6b5fe728ea55ba5bf
ms.sourcegitcommit: 626d485dae1e001e63e4d4bf78f6770766822ba0
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/06/2021
ms.locfileid: "7892396"
---
# <a name="manage-environments"></a>Behandle miljøer

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Bytt miljøer

Velg kontrollen **Miljø** øverst i høyre hjørne på siden for å endre miljøer.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Skjermbilde av kontrollen for å bytte miljø.":::

Administratorer kan [opprette](create-environment.md) og behandle miljøer.

## <a name="edit-an-existing-environment"></a>Redigere et eksisterende miljø

Du kan redigere noen av detaljene i eksisterende miljøer.

1.  Velg **Miljø**-velgeren i overskriften i appen.

2.  Velg **Rediger**-ikonet.

3. I **Rediger miljø**-boksen kan du oppdatere miljøinnstillingene.

Hvis du vil ha mer informasjon om miljøinnstillinger, kan du se [Opprette et nytt miljø](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Koble til Microsoft Dataverse
   
Trinnet **Microsoft Dataverse** lar deg koble til Customer Insights med Dataverse-miljøet.

For å bruke [standard prediksjonsmodeller](predictions-overview.md#out-of-box-models) konfigurerer du datadeling med Dataverse. Du kan også aktivere datainntak fra lokale datakilder og angi URL-adressen som Microsoft Dataverse-miljøet administrerer. Velg **Aktiver datadeling** for å dele Customer Insights-utdata med en Dataverse-administrert datasjø.

> [!IMPORTANT]
> Customer Insights og Dataverse må være i samme region for å aktivere datadeling.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Konfigurasjonsalternativer for å aktivere datadeling med Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights støtter ikke følgende datadelingsscenarioer:
> - Hvis du lagrer alle dataene til din egen Azure Data Lake Storage, vil du ikke kunne aktivere datadeling med en Dataverse-administrert datasjø.
> - Hvis du aktiverer datadeling med Dataverse, kan du ikke [opprette beregnede eller manglende verdier i en enhet](predictions.md).

## <a name="copy-the-environment-configuration"></a>Kopier miljøkonfigurasjonen

Når du oppretter et nytt miljø, kan du velge å kopiere konfigurasjonen fra et eksisterende miljø. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skjermbilde av innstillingsalternativene i miljøinnstillingene.":::

Det vises en liste over alle tilgjengelige miljøer i organisasjonen, der du kan kopiere data fra.

Følgende konfigurasjonsinnstillinger kopieres:

- Samlede/importerte datakilder
- Konfigurasjon av forening av data (tilordning, samsvar, sammenslåing)
- Segmenter
- Mål
- Relasjoner
- Aktiviteter
- Søk- og filterindeks
- Eksportmål
- Planlagt oppdatering
- Suppleringer
- Modelladministrasjon
- Rolletildelinger

Følgende data er *ikke* kopiert:

- Kundeprofiler.
- Legitimasjon for datakilde. Du må angi legitimasjonen for hver datakilde og oppdatere datakildene manuelt.

- Datakilder fra mappen Common Data Model og Dataverse-administrert datasjø. Du må opprette disse datakildene manuelt med samme navn som i kildemiljøet.

Når du kopierer et miljø, vises en bekreftelsesmelding om at det nye miljøet er opprettet. Velg **Gå til datakilder** for å vise listen over datakilder.

Alle datakildene vil vise statusen **Legitimasjon kreves**. Rediger datakildene, og angi legitimasjonen for å oppdatere dem.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste over datakilder som ble kopiert og trenger godkjenning.":::

Etter at du har oppdatert datakildene, går du til **Data** > **Samle**. Her finner du innstillinger fra kildemiljøet. Rediger dem etter behov, eller velg **Kjør** for å starte prosessen med datasamling og opprette den enhetlige kundeenheten.

Når datasamlingen er fullført, kan du gå til **Mål** og **Segmenter** for å oppdatere dem også.

## <a name="reset-an-existing-environment"></a>Tilbakestille et eksisterende miljø

Som en administrator kan du tilbakestille et miljø til en tom tilstand hvis du vil slette alle konfigurasjoner og fjerne data som er hentet inn.

1.  Velg **Miljø**-velgeren i overskriften i appen. 

2.  Velg miljøet du vil tilbakestille, og velg ellipsen (**...**). 

3. Velg **Tilbakestill**-alternativet. 

4.  Bekreft slettingen ved å skrive inn miljønavnet og velge **Tilbakestill**.

## <a name="delete-an-existing-environment"></a>Slette et eksisterende miljø

Som en administrator kan du slette et miljø du administrerer.

1.  Velg **Miljø**-velgeren i overskriften i appen.

2.  Velg miljøet du vil tilbakestille, og velg ellipsen (**...**). 

3. Velg **Slett**-alternativet. 

4.  Bekreft slettingen ved å angi miljønavnet og velge **Slett**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
