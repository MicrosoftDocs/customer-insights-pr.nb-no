---
title: Bruke datakildene til å ta inn data
description: Lær hvordan du importerer data fra ulike kilder.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595959"
---
# <a name="data-sources-overview"></a>Oversikt over datakilder

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Funksjonen for målgruppeinnsikt i Dynamics 365 Customer Insights kobler til data fra et bredt sett med kilder. Tilkobling til en datakilde kalles ofte *datainntak*. Når du har integrert dataene, kan du [samle](data-unification.md) og utføre handlinger på dataene.

## <a name="add-a-data-source"></a>Legg til en datakilde

Se i de detaljerte artiklene om hvordan du legger til en datakilde, avhengig av hvilket alternativ du velger.

Du kan legge til en datakilde på tre hovedmåter:

- [Gjennom dusinvis av Power Query-koblinger](connect-power-query.md)
- [Fra en mappe i Common Data Model](connect-common-data-model.md)
- [Fra din egen Common Data Service-datasjø](connect-common-data-service-lake.md)

> [!NOTE]
> Du kan ikke legge til data fra lokale datakilder ennå.

## <a name="review-ingested-data"></a>Se gjennom integrerte data

Du ser navnet på hver integrerte datakilde, statusen og siste gang dataene ble oppdatert for kilden. Du kan sortere listen over datakilder etter hver kolonne.

> [!div class="mx-imgBorder"]
> ![Tillagt datakilde](media/configure-data-datasource-added.png "Tillagt datakilde")

|Status  |Beskrivelse  |
|---------|---------|
|Vellykket   |Datakilden ble tatt inn hvis et klokkeslett er nevnt i **Oppdatert**-kolonnen.
|Ikke startet   |Datakilden har ingen data som er tatt inn ennå, eller den er fremdeles i utkastmodus.         |
|Oppdaterer    |Datainntak pågår. Du kan avbryte denne operasjonen ved å velge **Stopp oppdatering** i kolonnen **Handlinger**. Hvis du stopper oppdateringen av en datakilde, blir den tilbakestilt til siste oppdateringstilstand.       |
|Mislyktes     |Det oppstod en feil i datainnhentingen.         |

Velg verdien i **Status**-kolonnen for en datakilde for å se gjennom flere detaljer. Utvid **Datakilder** i ruten **Fremdriftsdetaljer**. Velg **Se detaljer** for mer informasjon om oppdateringsstatusen, inkludert informasjon om feil og prosessoppdateringer nedstrøms.

Datainnlasting kan ta litt tid. Etter en vellykket oppdatering kan de innhentede dataene gjennomgås fra siden **Enheter**. Hvis du vil ha mer informasjon, se [Enheter](entities.md).

## <a name="refresh-a-data-source"></a>Oppdatere en datakilde

Datakilder kan oppdateres etter en automatisk plan eller oppdateres manuelt ved behov. 

Gå til **Administrasjon** > **System** > [**Plan**](system.md#schedule-tab) for å konfigurere planlagte oppdateringer av alle datakilder som er tatt inn.

Følg denne fremgangsmåten for å oppdatere en datakilde ved behov:

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**

2. Velg den loddrette ellipsen ved siden av datakilden du vil oppdatere, og velg **Oppdater** fra rullegardinlisten.

3. Datakilden utløses nå for manuell oppdatering. Når du oppdaterer en datakilde, oppdateres både enhetsskjemaet og dataene for alle enhetene som er angitt i datakilden.

4. Velg **Stopp oppdatering** hvis du vil avbryte en eksisterende oppdatering, og datakilden tilbakestilles til den siste oppdateringsstatusen.

## <a name="delete-a-data-source"></a>Slette en datakilde

1. I Målgruppeinnsikt går du til **Data** > **Datakilder**.

2. Merk den loddrette ellipsen ved siden av datakilden du vil fjerne, og velg **Slett** fra rullegardinmenyen.

3. Bekreft slettingen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]