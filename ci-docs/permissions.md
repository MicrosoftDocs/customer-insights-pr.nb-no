---
title: Tilordne brukertillatelser
description: Lær om tillatelser og brukerroller.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245431"
---
# <a name="assign-user-permissions"></a>Tilordne brukertillatelser

Tilgang til Customer Insights er begrenset til brukere i organisasjonen som er lagt til i programmet av en administrator. En administrator kan legge til, redigere eller fjerne brukere. En bruker kan være én enkelt bruker, en gruppe eller et program. Det finnes tre typer roller som en bruker kan ha:

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
- Fullfør **Datasamling** som resulterer i enheten for enhetlig kundeprofil.
- Definere **Relasjoner** og **Aktiviteter**.
- Opprett segmenter ved hjelp siden **Segmenter**.
- Opprett mål ved hjelp siden **Mål**.
- Administrer konfigurasjon og suppler kundeprofiler fra **Supplering**-siden (bare for førsteparts suppleringer).
- Administrer og opprett eksporter basert på [tilkoblinger delt med bidragsytere](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administrator

- Alle tillatelser som er tilgjengelige for bidragsyteren.
- Endre innstillinger på siden **System**, inkludert arbeidsspråket, oppdater planer for systemprosessene og eksporter diagnoselogger.
- Endre innstillinger på siden **Sikkerhet**, inkludert brukere, API-nøkler, private koblinger og key vault.
- Angi søke- og filtreringdefinisjoner for Kunder-siden ved å bruke siden **Søk- og filterindeks** (tilgjengelig via **Kunder**-siden).
- Administrer tilkoblinger, og tillat dem for andre brukerroller på **Tilkoblinger**-siden.
- Administrer konfigurasjon og suppler kundeprofiler fra **Supplering**-siden (for alle suppleringer).
- Behandle og opprett eksporter på **Eksporter**-siden.
- Installere og bruk **Tillegg for kundekort**.
- Legg til og bruk **Power Apps-koblingen**.
- Aktiver bruk av [API-er for Customer Insights](apis.md).
- [Tilordne miljøeierskap](manage-environments.md#change-the-owner-of-an-environment) til en annen administrator.

## <a name="admin-owner"></a>Administrator (eier)

- Alle tillatelser som er tilgjengelige for administratoren.
- [Tilbakestill og slett](manage-environments.md#reset-an-existing-environment-preview) miljøet.

## <a name="add-users"></a>Legg til brukere

1. Gå til **Administrator** > **Sikkerhet**, og velg fanen **Brukere**.

1. Velg **Legg til brukere** for å åpne ruten **Legg til / rediger tillatelser**.

1. Bruk **Søk**-feltet til å finne Azure Active Directory-brukeren eller -gruppen som du vil legge til. Velg en **Rolle** som skal tilordnes brukeren eller gruppen.

1. Velg **Lagre**. Det gjeldende miljøet deles automatisk med brukeren eller medlemmene av gruppen. Brukere kan få tilgang til Customer Insights-appen og arbeide i henhold til den angitte rollen.

## <a name="view-current-permissions"></a>Vise gjeldende tillatelser

Gå til **Administrator** > **Sikkerhet**, og velg fanen **Brukere** for å vise listen over aktive brukere og deres rolletildelinger. Du kan sortere listen over brukere etter en hvilken som helst kolonne, eller du kan bruke søkefeltet til å finne en bestemt bruker.

## <a name="manage-current-users"></a>Administrer nåværende brukere

Gå til **Administrator** > **Sikkerhet** og velg fanen **Brukere**. Du kan sortere listen over suppleringer etter en hvilken som helst kolonne, eller du kan bruke søkefeltet til å finne suppleringen du vil administrere.

Velg en bruker for å vise tilgjengelige handlinger.

- **Rediger** for å redigere brukerens rolle i Customer Insights. Velg **Lagre** for å bekrefte endringen.
- **Fjern** for å fjerne brukeren fra å ha tilgang til Customer Insights. Velg **Slett** for å bekrefte slettingen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
