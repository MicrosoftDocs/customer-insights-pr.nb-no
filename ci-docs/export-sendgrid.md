---
title: Eksportere segmenter til SendGrid (forhåndsvisning)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197004"
---
# <a name="export-segments-to-sendgrid-preview"></a>Eksportere segmenter til SendGrid (forhåndsvisning)

Eksporter segmenter av enhetlige kundeprofiler til SendGrid-kontaktliser, og bruk dem for kampanjer og e-postmarkedsføring i SendGrid.

## <a name="prerequisites"></a>Forutsetning

- En [SendGrid-konto](https://sendgrid.com/) og tilhørende administratorlegitimasjon.
- [Eksisterende kontaktlister i SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) og de tilsvarende ID-ene.
- En [API-nøkkel for SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 100 000 kundeprofiler totalt til SendGrid, som kan ta opptil fem timer å fullføre. Antall kundeprofiler du kan eksportere til SendGrid, avhenger av kontrakten med SendGrid.
- Bare segmenter.

## <a name="set-up-connection-to-sendgrid"></a>Konfigurere tilkobling til SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **SendGrid**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **API-nøkkel for SendGrid**.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra SendGrid-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Angi **ID for SendGrid-liste**.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet.

1. Velg eventuelt felter, for eksempel **Fornavn**, **Etternavn**, **Land/område**, **Delstat**, **Sted** og **Postnummer**.

1. Velg segmentene du vil eksportere, basert på de kjente begrensningene.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
