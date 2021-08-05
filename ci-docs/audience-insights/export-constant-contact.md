---
title: Eksportere Customer Insights-data til Constant Contact
description: Lær hvordan du konfigurerer tilkoblingen og eksporten til Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b54659f028a141fe8f351645d96e933d47568a39
ms.sourcegitcommit: adb9c43ddaba25e511535d78a4bcf8815f154a7b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/06/2021
ms.locfileid: "6362430"
---
# <a name="export-segments-to-constant-contact-preview"></a>Eksportere segmenter til Constant Contact (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Constant Contact, og bruk dem for markedsføringsaktiviteter. 

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

-   Du har en [Constant Contact-konto](https://www.constantcontact.com/account-home) og tilhørende administratorlegitimasjon.
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Du kan eksportere opptil 1 million profiler per eksport til Constant Contact.
- Eksport til Constant Contact er begrenset til segmenter.
- Det kan ta opptil 1 time å eksportere 1 million profiler til Constant Contact. 
- Antall profiler du kan eksportere til Constant Contact, er avhengig av og begrenset av kontrakten med Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Konfigurer tilkobling til Constant Contact

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Constant Contact** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til Constant Contact.

1. Velg **Godkjenn med konstant kontakt**, og oppgi administratorlegitimasjonen for Konstant kontakt. 

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Constant Contact-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi [**liste-IDen for Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Åpne en liste i Constant Contact for å finne liste-IDen i URL-adressen.

1. I **Datasamsvar**-delen, i feltet **E-post** velger du feltet i den enhetlige kundeprofilen som representerer en kundes e-postadresse. Det kreves for å eksportere segmenter til Constant Contact.

1. Du kan eventuelt eksportere Fornavn og Etternavn som tilleggsfelt for å opprette mer tilpassede e-postmeldinger. Velg **Legg til attributt** for å tilordne disse feltene.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for å overføre data til Constant Contact, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, for eksempel personlige opplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at Constant Contact oppfyller eventuelle personvern- eller sikkerhetsforpliktelser du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
