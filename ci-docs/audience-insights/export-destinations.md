---
title: Eksportere data fra Customer Insights
description: Administrer eksporter for å dele data.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896155"
---
# <a name="exports-preview-overview"></a>Oversikt over Eksporter (forhåndsversjon)

**Eksporter**-siden viser alle konfigurerte eksporter. Eksporter deler bestemte data med forskjellige programmer. De kan omfatte kundeprofiler eller enheter, skjemaer og tilordningsdetaljer. Hver eksport krever en [tilkobling, konfigurert av en administrator, for å administrere godkjenning og tilgang](connections.md).

> [!NOTE]
> Frem til mars 2021 opprettet eksporter automatisk en tilkobling til den tilsvarende tjenesten. Eksporter krever nå en [tilkobling, opprettet og delt av en administrator](connections.md) før du kan opprette dem.

Gå til **Data** > **Eksporter** for å vise eksportsiden. Alle brukerroller har tilgang til å vise konfigurerte eksporter. Bruk av søkefeltet på kommandolinjen til å søke etter eksporter etter navn, tilkoblingsnavn eller tilkoblingstype.

## <a name="set-up-a-new-export"></a>Konfigurer en ny eksport

Hvis du vil konfigurere eller redigere en eksport, må du ha tilkoblinger tilgjengelige for deg. Tilkoblinger avhenger av [brukerrollen din](permissions.md):
- Administratorer har tilgang til alle tilkoblinger. De kan også opprette nye tilkoblinger når de konfigurerer en eksport.
- Bidragsytere kan ha tilgang til bestemte tilkoblinger. De er avhengig av administratorer for å konfigurere og dele tilkoblinger. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Visningsprogrammer kan bare vise eksisterende eksporter, men ikke opprette dem.

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport** for å opprette et nytt eksportmål.

1. Velg hvilken tilkobling som skal brukes, i ruten **Konfigurer eksport**. [Tilkoblinger](connections.md) administreres av administratorer. 

1. Oppgi de nødvendige detaljene, og velg **Lagre** for å opprette eksporten.

### <a name="edit-an-export"></a>Rediger en eksport

1. Velg den loddrette ellipsen for eksportmålet du vil redigere.

1. Velg **Rediger** i rullegardinlisten.

1. Endre verdiene du vil oppdatere, og velg **Lagre**.

## <a name="view-exports-and-export-details"></a>Vise eksporter og eksportdetaljer

Når du har opprettet eksportmål, vises de i **Data** > **Eksporter**. Alle brukere kan se hvilke data som deles, og den nyeste statusen.

1. Gå til **Data** > **Eksporter**.

1. Brukere uten redigeringstillatelser velger **Vis** i stedet for **Rediger** for å se eksportdetaljene.

1. Denne sideruten viser oppsettet for denne eksporten. Du kan ikke endre verdier uten redigeringstillatelser. Velg **Lukk** for å gå tilbake til eksportsiden.

## <a name="run-exports-on-demand"></a>Kjør eksporter ved behov

Når du har konfigurert en eksport, kjøres den med alle [planlagte oppdateringer](system.md#schedule-tab) så lenge den har en fungerende tilkobling.

Hvis du vil eksportere data uten å vente på en planlagt oppdatering, går du til **Data** > **Eksporter**. Du har to alternativer:

- Hvis du vil kjøre alle eksporter, velger du **Kjør alle** på kommandolinjen. 
- Hvis du vil kjøre én enkelt eksport, velger du ellipsen (...) på et listeelement, og deretter velger du **Kjør**.

## <a name="remove-an-export"></a>Fjerne en eksport

1. Gå til **Data** > **Eksporter**.

1. Velg den loddrette ellipsen for eksporten du vil fjerne.

1. Velg **Fjern** fra rullegardinmenyen.

1. Bekreft fjerningen ved å velge **Fjern** i bekreftelsesdialogboksen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
