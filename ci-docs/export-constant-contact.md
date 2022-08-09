---
title: Eksportere segmenter til Constant Contact (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporten til Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196498"
---
# <a name="export-segments-to-constant-contact-preview"></a>Eksportere segmenter til Constant Contact (forhåndsversjon)

Eksporter segmenter av enhetlige kundeprofiler til Constant Contact, og bruk dem for markedsføringsaktiviteter.

## <a name="prerequisites"></a>Forutsetning

- En [Constant Contact-konto](https://www.constantcontact.com/account-home) og tilhørende administratorlegitimasjon.
- En [ID for Constant Contact-liste](https://app.constantcontact.com/pages/contacts/ui#lists). Åpne en liste i Constant Contact for å finne liste-IDen i URL-adressen.
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million kundeprofiler per eksport til Constant Contact, som kan ta opptil en time å fullføre. Antall kundeprofiler du kan eksportere til Constant Contact, avhenger av kontrakten med Constant Contact.
- Bare segmenter.

## <a name="set-up-connection-to-constant-contact"></a>Konfigurer tilkobling til Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling** og velg **Constant Contact**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Godkjenn med konstant kontakt**, og oppgi administratorlegitimasjonen for Konstant kontakt.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra Constant Contact-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Angi **ID for Constant Contact-liste**.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet.

1. Eksporter eventuelt **Fornavn** og **Etternavn** som tilleggsfelt for å opprette mer tilpassede e-postmeldinger. Velg **Legg til attributt** for å tilordne disse feltene.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
