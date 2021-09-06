---
title: Tilkoblinger til andre tjenester fra Customer Insights.
description: Del data med andre tjenester.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 37c5d152a4cc91a90df8db387d25923ed150e238bc6b54c54f7bba59fbd48c82
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033230"
---
# <a name="connections-preview-overview"></a>Oversikt over tilkoblinger (forhåndsversjon)

Tilkoblinger er nøkkelen til å aktivere datadeling til og fra Customer Insights. Hver tilkobling oppretter datadeling med en bestemt tjeneste. Tilkoblinger er grunnlaget for å [konfigurere suppleringer fra tredjeparter](enrichment-hub.md) og [konfigurere eksporter](export-destinations.md). Den samme tilkoblingen kan brukes flere ganger. Én tilkobling til Dynamics 365 Marketing fungerer for eksempel for flere eksporter, og én Leadspace-tilkobling kan brukes til flere suppleringer.

Gå til **Administrator** > **Tilkoblinger** for å opprette og vise tilkoblinger.

Kategorien **Tilkoblinger** viser alle aktive tilkoblinger. Listen viser en rad for hver tilkobling. 

Få en rask oversikt, beskrivelse og finn ut hva du kan gjøre med hvert utvidelsesalternativ i kategorien **Oppdag**.

### <a name="exports"></a>Eksporter

Bare administratorer kan konfigurere nye tilkoblinger, men de kan gi tilgang til bidragsytere for å bruke eksisterende tilkoblinger. Administratorer kontrollerer hvor data kan gå, bidragsytere definerer nyttelasten og frekvensen som passer til deres behov. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Suppleringer

Bare administratorer kan konfigurere nye tilkoblinger, men de opprettede tilkoblingene er alltid tilgjengelige for både administratorer og bidragsytere. Administratorer administrerer legitimasjon og gir samtykke til dataoverføringer. Tilkoblingene kan deretter brukes til suppleringer av både administratorer og bidragsytere.

## <a name="add-a-new-connection"></a>Legg til en ny tilkobling

Hvis du vil legge til tilkoblinger, må du ha [administratortillatelser](permissions.md). Hvis du kobler til andre Microsoft-tjenester, antar vi at begge tjenestene er i samme organisasjon.

1. Gå til **Administrator** > **Tilkoblinger (forhåndsversjon)**.

1. Gå til kategorien **Tilkoblinger**.

1. Velg **Legg til tilkobling** for å opprette en ny tilkobling. Velg hvilken tilkoblingstype du vil opprette, i rullegardinmenyen.

1. Angi de nødvendige detaljene i ruten **Konfigurer tilkobling**. 
   1. **Visningsnavnet** og tilkoblingstypen beskriver en tilkobling. Vi anbefaler at du velger et navn som forklarer formålet med og målet for denne tilkoblingen.
   1. De nøyaktige feltene avhenger av hvilken tjeneste du kobler til. Du kan lære om detaljer om en bestemt tilkoblingstype i artikkelen om måltjenesten.

1. Velg **Lagre** for å opprette tilkoblingen.

Du kan også velge **Konfigurer** på en flis i kategorien **Oppdag**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Tillat bidragsytere å bruke en tilkobling for eksporter

Når du definerer eller redigerer en eksporttilkobling, velger du hvilke brukere som har tillatelse til å bruke denne bestemte tilkoblingen til å definere [eksporter](export-destinations.md). Som standard er en tilkobling tilgjengelig for brukere med en administratorrolle. Du kan endre denne innstillingen under **Velg hvem som kan bruke denne tilkoblingen**, og la brukere med bidragsyterrolle bruke denne tilkoblingen.

- Bidragsytere kan ikke vise eller redigere tilkoblingen. De vil bare se visningsnavn og dens type når du oppretter en eksport.
- Ved å dele en tilkobling tillater du at bidragsytere bruker en tilkobling. Bidragsytere vil se delte tilkoblinger når de konfigurerer eksporter. De kan administrere hver eksport som bruker denne spesifikke tilkoblingen.
- Du kan endre denne innstillingen samtidig som du beholder eksportene som allerede er definert av bidragsytere.

## <a name="edit-a-connection"></a>Redigere en tilkobling

1. Gå til **Administrator** > **Tilkoblinger (forhåndsversjon)**.

1. Gå til kategorien **Tilkoblinger**.

1. Velg den loddrette ellipsen for tilkoblingen du vil redigere.

1. Velg **Rediger**.

1. Endre verdiene du vil oppdatere, og velg **Lagre**.

## <a name="remove-a-connection"></a>Fjerne en tilkobling

Hvis tilkoblingen du fjerner, brukes av suppleringer eller eksport, må du først koble fra eller fjerne dem. Dialogboksen for fjerning vil lede deg til de relevante suppleringene eller eksportene. 

Frakoblede suppleringer og eksporter blir inaktive. Du aktiverer dem på nytt ved å legge til en annen tilkobling til dem på siden [Suppleringer](enrichment-hub.md) eller [Eksporter](export-destinations.md).

1. Gå til **Administrator** > **Tilkoblinger (forhåndsversjon)**.

1. Gå til kategorien **Tilkoblinger**.

1. Velg den loddrette ellipsen for tilkoblingen du vil fjerne.

1. Velg **Fjern** fra rullegardinmenyen. En bekreftelsesdialogboks vises.

   1. Hvis det er suppleringer eller eksporterer som bruker denne tilkoblingen, velger du knappen for å se hva som bruker tilkoblingen.
      - **Eksporter:** Du kan velge å fjerne eller koble fra eksportene for å kunne fjerne tilkoblingen. Administratorer kan bruke **Koble fra**-handlingen for å koble fra en eksport. Denne handlingen er tilgjengelig for individuelle og flere valgte eksporter. Ved å koble fra beholder du eksportkonfigurasjonen, men den kjøres ikke før en annen tilkobling er lagt til i den.
      - **Suppleringer:** Du kan velge å fjerne eller deaktivere suppleringene for å kunne fjerne tilkoblingen. 
   1. Når tilkoblingen ikke har flere avhengigheter, går du tilbake til **Administrator** > **Tilkoblinger** og prøver å fjerne tilkoblingen på nytt.

1. Velg **Fjern** for å bekrefte slettingen.

