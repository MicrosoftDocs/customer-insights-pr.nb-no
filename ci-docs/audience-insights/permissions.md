---
title: Administrasjon av brukertillatelser
description: Lær om tillatelser og brukerroller.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a3d21d55d86950953611967bb66712312eb42b4b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355949"
---
# <a name="user-permissions"></a>Brukertillatelser

På **Tillatelser**-siden kan du konfigurere roller og tillatelser for bruk av målgruppeinnsikt.

Du må ha administratortillatelse for å se siden. For å få tilgang til tillatelsessiden i målgruppeinnsikt går du til **Administrasjon** > **Tillatelser**.

Det finnes tre typer roller:

## <a name="viewer"></a>Visningsprogram

- Utforsk innsikt og segmenter på sidene **Start** og **Segmenter**.
- Søk etter og filtrer kundeprofiler på siden **Kunder**. Feltene må være søkbare.
- Vise og utforske siden **Supplering**.
- Utforsk og eksporter enheter på siden **Enheter**.
- Vis statusen for systemprosesser ved hjelp av siden **System**.
- Vis eksporter på **Eksporter**-siden.
- Installer og bruk instrumentbordet i **Power BI Customer Insights**.

## <a name="contributor"></a>Bidragsyter

- Alle tillatelser som er tilgjengelige for visningsprogrammet.
- Last inn og transformer data ved hjelp av siden **Datakilder**.
- Fyll ut delene *Datasamling* (**Tilordne**, **Samsvar** og **Slå sammen**), som fører til en samlet kundeprofilenhet.
- Definere **Relasjoner** og **Aktiviteter**.
- Opprett segmenter ved hjelp siden **Segmenter**.
- Opprett mål ved hjelp siden **Mål**.
- Administrer konfigurasjon og suppler kundeprofiler fra **Supplering**-siden (bare for førsteparts suppleringer).
- Administrer og opprett eksporter basert på tilkoblinger delt med bidragsytere. [Lær mer om hvordan administratorer tillater at bidragsytere bruker en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Administrator

- Alle tillatelser som er tilgjengelige for bidragsyteren.
- Endre innstillinger på siden **System**, inkludert arbeidsspråket, og oppdater planer for systemprosessene.
- Vis og legg til tillatelser ved hjelp av siden **Tillatelser**.
- Angi søke- og filtreringdefinisjoner for Kunder-siden ved å bruke siden **Søk- og filterindeks** (tilgjengelig via **Kunder**-siden).
- Administrer tilkoblinger, og tillat dem for andre brukerroller på **Tilkoblinger**-siden.
- Administrer konfigurasjon og suppler kundeprofiler fra **Supplering**-siden (for alle suppleringer).
- Behandle og opprett eksporter på **Eksporter**-siden.
- Installere og bruk **Tillegg for kundekort**.
- Legg til og bruk **Power Apps-koblingen**.
- Aktiver bruk av [API-er for Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Tilordne roller og tillatelser

1. I Målgruppeinnsikt går du til **Administrasjon** > **Tillatelser**.

1. Velg **Legg til brukere** for å åpne ruten **Legg til / rediger tillatelser**.

1. Bruk **Søk**-feltet til å finne Azure Active Directory-brukeren eller -gruppen som du vil justere tillatelser for. Velg en **Rolle** som skal tilordnes brukeren eller gruppen.

1. Velg **Lagre**. Det gjeldende miljøet deles automatisk med brukeren eller medlemmene av gruppen som du har endret tillatelser for. Brukere kan få tilgang til Customer Insights-appen og arbeide i henhold til den angitte rollen.

## <a name="view-current-permissions"></a>Vise gjeldende tillatelser

I målgruppeinnsikt går du til **Administrasjon** > **Tillatelser** for å se hvilke rolletildelinger som er aktive for øyeblikket.

- Kolonnen **Type** angir én bruker, én gruppe eller ett program. Systemet støtter individuelle brukere og grupper.
- Roller er angitt under kolonnen **Rolle**.
- Velg en kolonnetittel for å sortere resultatene etter verdien i kolonnen.
- Bruk **Søk**-feltet øverst på siden for å finne bestemte brukere.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
