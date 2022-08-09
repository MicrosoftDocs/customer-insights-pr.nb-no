---
title: Eksportere segmenter til DotDigital (forhåndsversjon)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196084"
---
# <a name="export-segments-to-dotdigital-preview"></a>Eksportere segmenter til DotDigital (forhåndsversjon)

Eksporter segmenter med enhetlige kundeprofiler til DotDigital-adressebøker, og bruk dem for kampanjer, e-postmarkedsføring og til å bygge kundesegmenter med DotDigital.

## <a name="prerequisites"></a>Forutsetning

- En [DotDigital-konto](https://dotdigital.com/) og en [API-bruker](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- En DotDigital-ID fra en [ny](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) eller eksisterende adressebok i DotDigital. Du kan finne ID-en i URL-adressen når du velger og åpner en adressebok.
- [Konfigurerte segmenter](segments.md) i Customer Insights.
- Enhetlige kundeprofiler i de eksporterte segmentene inneholder et felt som representerer en e-postadresse.

## <a name="known-limitations"></a>Kjente begrensninger

- Opptil 1 million kundeprofiler per eksport til DotDigital, som kan ta opptil tre timer å fullføre på grunn av begrensninger på leverandørsiden. Antall kundeprofiler du kan eksportere til DotDigital, avhenger av kontrakten med DotDigital.
- Bare segmenter.

## <a name="set-up-connection-to-dotdigital"></a>Konfigurere tilkobling til DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **DotDigital**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angi **brukernavnet og passordet for DotDigital-API**.

1. Angi **ID for DotDigital-adressebok**.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Koble til** for å initialisere tilkoblingen.

1. Velg **Legg til deg selv som eksportbruker**, og angi Customer Insights-legitimasjonen din.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra DotDigital-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg feltet som representerer en kundes e-postadressen, i delen **Datasamsvar** i **E-post**-feltet.

1. Eksporter eventuelt **Fornavn**, **Etternavn**, **Fullt navn**, **Kjønn** og **Postnummer**.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

I DotDigital finner du segmentene i [DotDigital-adressebøker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
