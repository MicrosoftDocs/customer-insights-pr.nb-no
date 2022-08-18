---
title: Oversikt over tilkoblinger (forhåndsversjon)
description: Tilkoblinger til andre tjenester fra Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245523"
---
# <a name="connections-preview-overview"></a>Oversikt over tilkoblinger (forhåndsversjon)

Tilkoblinger er nøkkelen til å aktivere datadeling til og fra Customer Insights. Hver tilkobling oppretter datadeling med en bestemt tjeneste. Bruk tilkoblinger til å [konfigurere suppleringer fra tredjeparter](enrichment-hub.md) og [konfigurere eksporter](export-destinations.md). Den samme tilkoblingen kan brukes flere ganger. Én tilkobling til Dynamics 365 Marketing fungerer for eksempel for flere eksporter, og én Leadspace-tilkobling kan brukes til flere suppleringer.

## <a name="export-connections"></a>Eksporttilkoblinger

Bare administratorer kan konfigurere nye tilkoblinger, men de kan [gi tilgang til bidragsytere](#allow-contributors-to-use-a-connection-for-exports) for å bruke eksisterende tilkoblinger. Administratorer kontrollerer hvor data kan gå, bidragsytere definerer nyttelasten og frekvensen som passer til deres behov.

## <a name="enrichment-connections"></a>Suppleringstilkoblinger

Bare administratorer kan konfigurere nye tilkoblinger, men de opprettede tilkoblingene er alltid tilgjengelige for både administratorer og bidragsytere. Administratorer administrerer legitimasjon og gir samtykke til dataoverføringer. Tilkoblingene kan deretter brukes til suppleringer av både administratorer og bidragsytere.

## <a name="add-a-new-connection"></a>Legg til en ny tilkobling

### <a name="prerequisites"></a>Forutsetning

- [Administratorrettigheter](permissions.md)
- Andre Microsoft-tjenester, hvis noen, er i samme organisasjon

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg typen tilkobling du vil opprette. Du kan også gå til fanen **Oppdag** og velge **Konfigurer** på en tilkoblingsflis.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Angi de nødvendige detaljene. De nøyaktige feltene avhenger av hvilken service du kobler til. For detaljer om en bestemt tilkoblingstype kan du se artikkelen om måltjenesten.

1. Hvis du [bruker ditt eget Key Vault](use-azure-key-vault.md) til å lagre hemmeligheter, aktiverer du **Bruk Key Vault** og velger hemmeligheten fra listen.

1. Se gjennom datapersonvern og -samsvar, og velg **Jeg godtar**.

1. Velg **Lagre** for å opprette tilkoblingen.

### <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for å overføre data til tredjeparter eller andre Microsoft-produkter, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at tredjeparten oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne tilkoblingen når som helst for å slutte å bruke funksjonaliteten.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Tillat bidragsytere å bruke en tilkobling for eksporter

Når du definerer eller redigerer en eksporttilkobling, velger du hvilke brukere som har tillatelse til å bruke denne bestemte tilkoblingen til å definere [eksporter](export-destinations.md). Som standard er en tilkobling tilgjengelig for brukere med en administratorrolle. Endre innstillingen **Velg hvem som kan bruke denne tilkoblingen** for å la brukere med bidragsyterrolle bruke denne tilkoblingen.

- Bidragsytere kan ikke vise eller redigere tilkoblingen. De ser bare datatypen og visningsnavnet ved oppretting av en eksport.
- Ved å dele en tilkobling tillater du at bidragsytere bruker en tilkobling. Bidragsytere vil se delte tilkoblinger når de konfigurerer eksporter. De kan administrere hver eksport som bruker denne spesifikke tilkoblingen.
- Du kan endre denne innstillingen samtidig som du beholder eksportene som allerede er definert av bidragsytere.

## <a name="manage-existing-connections"></a>Behandle eksisterende tilkoblinger

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg fanen **Supplering** eller **Eksporter** for å vise en liste over supplerings- eller eksporttilkoblinger, tilkoblingstypen, når den ble opprettet, og hvem som har tilgang. Du kan sortere listen over koblinger etter en kolonne.

1. Velg tilkoblingen for å vise tilgjengelige handlinger.

   - **Rediger** koblingen.
   - [**Fjern**](#remove-a-connection) en tilkobling.

### <a name="remove-a-connection"></a>Fjerne en tilkobling

Hvis tilkoblingen du fjerner, brukes av suppleringer eller eksporter, må du først koble fra eller fjerne dem. Dialogboksen for fjerning leder deg til de relevante suppleringene eller eksportene.

> [!TIP]
> Deaktiverte suppleringer og frakoblede eksporter blir inaktive. Du aktiverer dem på nytt ved å legge til en annen tilkobling til dem på siden [Suppleringer](enrichment-hub.md) eller [Eksporter](export-destinations.md).

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg fanen **Supplering** eller **Eksporter**.

1. Velg koblingen du vil fjerne.

1. Velg **Fjern** fra rullegardinmenyen. En bekreftelsesdialogboks vises.

   1. Hvis det er suppleringer eller eksporterer som bruker denne tilkoblingen, velger du knappen for å se hva som bruker tilkoblingen.
      - **Eksporter:** Velg å **fjerne** eksporten eller **koble fra** tilkoblingen. Frakobling av koblingen beholder eksportkonfigurasjonen, men den kjøres ikke før en annen tilkobling er lagt til i den.
      - **Suppleringer:** Velg å **slette** eller **deaktivere** suppleringene.
   1. Når tilkoblingen ikke har flere avhengigheter, går du tilbake til **Administrator** > **Tilkoblinger** og prøver å fjerne tilkoblingen på nytt.

1. Velg **Fjern** for å bekrefte slettingen.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Konfigurere tilkoblinger med hemmeligheter administrert av din egen Key Vault

Noen tilkoblinger trenger hemmeligheter, for eksempel API-nøkler eller passord. Noen tilkoblinger støtter hemmeligheter lagret i din egen Key Vault. Finn ut mer om støttede tilkoblinger og hvordan du konfigurerer i [ditt eget Key Vault for Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
