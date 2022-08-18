---
title: Suppler kundeprofiler med egendefinert SFTP-import (forhåndsversjon)
description: Generell informasjon om supplering med egendefinert SFTP-import.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237778"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Suppler kundeprofiler med egendefinert SFTP-import (forhåndsversjon)

Med egendefinert SFTP-import (Secure File Transfer Protocol) kan du importere data som ikke trenger å gå gjennom dataforening. Det er en fleksibel, sikker og enkel måte å skaffe seg på dataene på. Egendefinert SFTP-import kan brukes i kombinasjon med [SFTP-eksport](export-sftp.md), noe som gjør at du kan eskportere kundeprofildataene som er nødvendig for supplering. Dataene kan deretter behandles og forbedres, og tilpasset SFTP-import kan brukes til å hente de supplerte dataene tilbake til Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Forutsetning

- Filnavn og plassering (bane) for filen som skal importeres på SFTP-verten, er kjent.

- En *model.json*-fil som angir Common Data Model-skjemaet for dataene som skal importeres, er tilgjengelig. Denne filen må være i samme katalog som filen som skal importeres.

- En SFTP-[tilkobling](connections.md) er [konfigurert](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Eksempel på filskjema

Katalogen som inneholder filen som skal importeres på SFTP-serveren, må også inneholde en *model.json*-fil. Denne filen definerer skjemaet som skal brukes til å importere dataene. Skjemaet må bruke [Common Data Model](/common-data-model/) for å angi felttilordningen. Et enkelt eksempel på en model.json-fil ser slik ut:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurere tilkoblingen for egendefinert import av SFTP

Du må være en [administrator](permissions.md#admin) i Customer Insights og ha brukerlegitimasjonen, nettadressen og portnummeret for SFTP-plasseringen der du vil importere data fra.

1. Velg **Legg til tilkobling** når du konfigurerer en supplering eller gå til **Administrasjon** > **Tilkoblinger** og velg **Konfigurer** i Egendefinert import-flisen.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Side for Egendefinert import-tilkoblingskonfigurasjon.":::

1. Skriv inn et navn for tilkoblingen.

1. Angi et gyldig brukernavn, passord og verts-URL for SFTP-serveren som dataene som skal importeres, finnes på.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Bekreft** for å validere konfigurasjonen, og velg deretter **Lagre**.

## <a name="configure-the-import"></a>Konfigurer importen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. Velg **Suppler dataene** på flisen **SFTP-egendefinert import**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Flis for egendefinert SFTP-import.":::

1. Se gjennom oversikten, og velg deretter **Neste**.

1. Velg tilkoblingen. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Velg **kundedatasettet** og velg profilen eller segmentet du vil supplere. *Kunde*-enheten supplerer alle kundeprofilene dine, mens segmentsuppleringer bare supplerer kundeprofiler i det segmentet.

1. Velg **Neste**.

1. Skriv inn **banen** og **filnavnet** til datafilen du vil importere.

1. Velg **Neste**.

1. Angi et **Navn** for suppleringen og **Utdataenhetsnavn**.

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

1. Velg **Kjør** for å starte suppleringsprosessen, eller lukk for å gå tilbake til siden **Suppleringer**.

## <a name="view-enrichment-results"></a>Vis suppleringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Neste trinn

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
