---
title: Eksportere segmenter til Sendinblue (forhåndsvisning)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724906"
---
# <a name="export-segments-to-sendinblue-preview"></a>Eksportere segmenter til Sendinblue (forhåndsvisning)

Eksporter segmenter for enhetlige kundeprofiler for å generere kampanjer, levere e-postmarkedsføring og bruke bestemte kundegrupper med Sendinblue.

## <a name="prerequisites"></a>Forutsetning

- En [Sendinblue-konto](https://www.sendinblue.com/) og tilsvarende administratorlegitimasjon.
- En [API-nøkkel for SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Eksisterende lister i Sendinblue og de tilhørende ID-ene.
- [Konfigurerte segmenter](segments.md).
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Private Link kombinert med Bring your own storage (BYOS) støttes ikke.
- Opptil 1 million kundeprofiler per eksport til Sendinblue, som kan ta opptil 90 minutter å fullføre. Antall kundeprofiler du kan eksportere til Sendinblue, avhenger av kontrakten med Sendinblue.
- Bare segmenter.

## <a name="set-up-connection-to-sendinblue"></a>Konfigurere tilkobling til Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Sendinblue**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **API-nøkkel for SendinBlue**.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg feltet **Tilkobling for eksport**, og velg en tilkobling fra Sendinblue-delen. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Angi **Liste-ID for Sendinblue**.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet.

1. Eksporter eventuelt **Fornavn**, **Etternavn** og **Telefon** for å opprette mer tilpassede e-postmeldinger. Velg **Legg til attributt** for å tilordne disse feltene.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
