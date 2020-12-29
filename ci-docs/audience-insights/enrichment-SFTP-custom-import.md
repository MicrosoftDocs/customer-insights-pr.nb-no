---
title: Supplering med egendefinert SFTP-import
description: Generell informasjon om supplering med egendefinert SFTP-import.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568480"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Supplere kundeprofiler med egendefinerte data (forhåndsversjon)

Med egendefinert SFTP-import (Secure File Transfer Protocol) kan du importere data som ikke trenger å gå gjennom dataforening. Det er en fleksibel, sikker og enkel måte å skaffe seg på dataene på. Egendefinert SFTP-import kan brukes i kombinasjon med [SFTP-eksport](export-sftp.md), noe som gjør at du kan eskportere kundeprofildataene som er nødvendig for supplering. Dataene kan deretter behandles og suppleres, og den egendefinerte SFTP-importen kan brukes til å hente de supplerte dataene tilbake til målgruppeinnsikt i Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Forutsetninger

For å konfigure egendefinert SFTP-import må følgende forhåndskrav være oppfylt:

- Du har brukerlegitimasjon (brukernavn og passord) for SFTP-plasseringen der dataene som skal importeres, ligger.
- Du har URL-adressen og portnummeret (vanligvis 22) for STFP-verten.
- Du har filnavnet og plasseringen til filen som skal importeres på SFTP-verten.
- Det finnes en *model.json*-fil som angir skjemaet for dataene som skal importeres. Denne filen må være i samme katalog som filen som skal importeres.
- Du har [administratortillatelser](permissions.md#administrator).

## <a name="configuration"></a>Konfigurasjon

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. På **flisen for egendefinert SFTP-import** velger du **Suppler dataene**.

   > [!div class="mx-imgBorder"]
   > ![Flis for egendefinert SFTP-import](media/SFTP_Custom_Import_tile.png "Flis for egendefinert SFTP-import")

1. Velg **Kom i gang**, og angi legitimasjonen og adressen for SFTP-serveren. Eksempel: sftp://mysftpserver.com:22.

1. Skriv inn navnet på filen som inneholder dataene, og banen til filen på SFTP-serveren hvis den ikke finnes i rotmappen.

1. Bekreft alle inndata ved å velge **Koble til egendefinert import**.

   > [!div class="mx-imgBorder"]
   > ![Undermeny for konfigurasjon av egendefinert SFTP-import](media/SFTP_Custom_Import_Configuration_flyout.png "Undermeny for konfigurasjon av egendefinert SFTP-import")

## <a name="defining-field-mappings"></a>Definere felttilordninger 

Katalogen som inneholder filen som skal importeres på SFTP-serveren, må også inneholde en *model.json*-fil. Denne filen definerer skjemaet som skal brukes til å importere dataene. Skjemaet må bruke [Common Data Model](https://docs.microsoft.com/common-data-model/) for å angi felttilordningen. Et enkelt eksempel på en model.json-fil ser slik ut:

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
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
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

## <a name="enrichment-results"></a>Resultater av supplering

Hvis du vil starte den omfattende prosessen, velger du **Kjør** fra kommandolinjen. Du kan også la systemet kjøre supplementet automatisk som en del av en [planlagt oppdatering](system.md#schedule-tab). Behandlingstiden avhenger av størrelsen på dataene som skal importeres, og tilkoblingen til SFTP-serveren.

Når suppleringsprosessen er fullført, kan du se gjennom de nylig importerte egendefinerte suppleringsdataene under **Mine suppleringer**. I tillegg finner du tidspunktet for den siste oppdateringen og antall supplerte profiler.

Du kan få tilgang til en detaljert visning av hver supplerte profil ved å velge **Vis supplerte data**.

## <a name="next-steps"></a>Neste trinn

Bygg på toppen av de supplerte kundedataene. Opprett [segmenter](segments.md) og [mål](measures.md), og [eksporter dataene](export-destinations.md) for å levere tilpassede opplevelser til kundene.


