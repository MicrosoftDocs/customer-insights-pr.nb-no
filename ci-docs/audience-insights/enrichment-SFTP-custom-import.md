---
title: Supplering med egendefinert SFTP-import
description: Generell informasjon om supplering med egendefinert SFTP-import.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 042558af801a1d1fc365939d9aa42c09b98b2679
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376612"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Supplere kundeprofiler med egendefinerte data (forhåndsversjon)

Med egendefinert SFTP-import (Secure File Transfer Protocol) kan du importere data som ikke trenger å gå gjennom dataforening. Det er en fleksibel, sikker og enkel måte å skaffe seg på dataene på. Egendefinert SFTP-import kan brukes i kombinasjon med [SFTP-eksport](export-sftp.md), noe som gjør at du kan eskportere kundeprofildataene som er nødvendig for supplering. Dataene kan deretter behandles og suppleres, og tilpasset SFTP-import kan brukes for å hente de supplerte dataene tilbake til målgruppeinnsiktsmulighetene i Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Forutsetninger

For å konfigure egendefinert SFTP-import må følgende forhåndskrav være oppfylt:

- Du har filnavnet og plasseringen (banen) til filen som skal importeres til SFTP-verten.
- Det finnes en *model.json*-fil som angir [Common Data Model-skjemaet](/common-data-model/) for dataene som skal importeres. Denne filen må være i samme katalog som filen som skal importeres.
- En SFTP-tilkobling er allerede konfigurert av en *administrator*, eller du har [administrator](permissions.md#admin)-tillatelser. Du trenger legitimasjonen for brukeren, URL-adressen og portnummeret for SFTP-plasseringen der du vil importere data fra.


## <a name="configure-the-import"></a>Konfigurer importen

1. Gå til **Data** > **Supplering**, og velg **Oppdag**-fanen.

1. På **flisen for egendefinert SFTP-import** velger du **Suppler dataene** og deretter **Kom i gang**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Flis for egendefinert SFTP-import.":::

1. Velg en [tilkobling](connections.md) fra rullegardinlisten. Kontakt en administrator hvis ingen tilkobling er tilgjengelig. Hvis du er en administrator, kan du opprette en tilkobling ved å velge **Legg til tilkobling** og velge **tilpasset SFTP-import** fra rullegardinlisten.

1. Velg **Koble til egendefinert import** for å bekrefte valget av tilkobling.

1.  Velg **Neste**, og angi **Bane** og **Filnavn** for datafilen du vil importere.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Skjermbilde når du angir dataplassering.":::

1. Velg **Neste**, og velg kundedatasettet. Dette kan enten være alle kundeprofiler eller et segment.

1. Velg **Neste** angi et navn for suppleringen og et navn for utdataenheten. 

1. Velg **Lagre supplering** etter at du har sett gjennom valgene.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurere tilkoblingen for egendefinert import av SFTP 

Du må være en administrator for å konfigurere tilkoblinger. Velg **Legg til tilkobling** når du konfigurerer en supplering *eller* gå til **Administrasjon** > **Tilkoblinger** og velg **Konfigurer** i Egendefinert import-flisen.

1. Skriv inn et navn på tilkoblingen i **Visningsnavn**-boksen.

1. Angi et gyldig brukernavn, passord og verts-URL for SFTP-serveren som dataene som skal importeres, finnes på.

1. Les gjennom og gi samtykke til **Datapersonvern og -samsvar** ved å merke av for **Jeg godtar**.

1. Velg **Bekreft** for å validere konfigurasjonen.

1. Når verifiseringen er fullført, kan tilkoblingen lagres ved å velge **Lagre**.

   > [!div class="mx-imgBorder"]
   > ![Experian-tilkoblingskonfigurasjonsside.](media/enrichment-SFTP-connection.png "Experian-tilkoblingskonfigurasjonsside")


## <a name="defining-field-mappings"></a>Definere felttilordninger 

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

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
