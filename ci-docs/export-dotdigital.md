---
title: Eksportere Customer Insights-data til DotDigital
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f63a0f5f5f93e96681a88fd758381c012a404f43
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646492"
---
# <a name="export-segments-to-dotdigital-preview"></a>Eksportere segmenter til DotDigital (forhåndsversjon)

Eksporter segmenter med enhetlige kundeprofiler til DotDigital-adressebøker, og bruk dem for kampanjer, e-postmarkedsføring og til å bygge kundesegmenter med DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

-   Du har en [DotDigital-konto](https://dotdigital.com/) og opprettet en [API-bruker](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Du må bruke API-brukerlegitimasjonen for å opprette en tilkobling
-   Det finnes eksisterende adressebøker i DotDigital og de tilsvarende ID-ene. Du kan finne ID-en i URL-adressen når du velger og åpner en adressebok. Hvis du vil ha mer informasjon, kan du se [DotDigital-adressebøker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Du har [konfigurerte segmenter](segments.md) i Customer Insights.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million kundeprofiler per eksport til DotDigital.
- Eksport til DotDigital er begrenset til segmenter.
- Eksport av segmenter med totalt 1 million kundeprofiler kan ta opptil 3 timer på grunn av begrensninger på leverandørsiden. 
- Antall kundeprofiler du kan eksportere til DotDigital, avhenger av og begrenses til kontrakten med DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Konfigurere tilkobling til DotDigital

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **DotDigital** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **brukernavnet og passordet for DotDigital-API**. 

1. Angi **[ID-en for DotDigital-adresseboken](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til DotDigital.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra DotDigital-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.


1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**, **Fullt navn**, **Kjønn** og **Postnummer**.

1. Velg segmentene du vil eksportere. Du kan eksportere opptil 1 million kundeprofiler totalt til DotDigital.

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 
 
I DotDigital kan du nå finne segmentene i [DotDigital-adressebøker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til DotDigital, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at DotDigital oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE [footer-include](includes/footer-banner.md)]
