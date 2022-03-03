---
title: Eksportere Customer Insights-data til SendGrid
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 65d60e7e70e3444b0695b905431bab9a0269ceef
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231584"
---
# <a name="export-segments-to-sendgrid-preview"></a>Eksportere segmenter til SendGrid (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til SendGrid-kontaktliser, og bruk dem for kampanjer og e-postmarkedsføring i SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Forutsetninger for en tilkobling

-   Du har en [SendGrid-konto](https://sendgrid.com/) og tilhørende påloggingsinformasjon for administrator.
-   Det finnes eksisterende kontaktlister i SendGrid og de tilsvarende ID-ene. Hvis du vil ha mer informasjon, kan du se [SendGrid – administrer kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Du har [konfigurerte segmenter](segments.md) i målgruppeinnsikt.
-   Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Totalt opptil 100 000 kundeprofiler til SendGrid.
- Eksport til SendGrid er begrenset til segmenter.
- Eksport av opptil 100 000 kundeprofiler til SendGrid kan ta opptil fem timer å fullføre. 
- Antall kundeprofiler du kan eksportere til SendGrid, avhenger av og begrenses til kontrakten med SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Konfigurere tilkobling til SendGrid

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **SendGrid** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **API-nøkkelen for SendGrid** [API-nøkkel for SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Koble til** for å initialisere tilkoblingen til SendGrid.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra SendGrid-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Angi **[ID-en for SendGrid-listen](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet. Gjenta de samme trinnene for andre valgfrie felt, for eksempel **Fornavn**, **Etternavn**, **Land/område**, **Delstat**, **Sted** og **Postnummer**.

1. Velg segmentene du vil eksportere. Vi **anbefaler på det sterkeste at du ikke eksporterer mer enn 100 000 kundeprofiler totalt** til SendGrid. 

1. Velg **Lagre**.

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data til SendGrid, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personopplysninger. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at SendGrid oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
