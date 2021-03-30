---
title: Eksportere Customer Insights-data til SFTP-verter
description: Lær hvordan du konfigurerer tilkoblingen til en SFTP-vert.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598397"
---
# <a name="connector-for-sftp-preview"></a>Kobling for SFTP (forhåndsversjon)

Bruk kundedata i tredjepartsprogrammer ved å eksportere dem til en SFTP-vert (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Forutsetninger

- Tilgjengelighet av en SFTP-vert og tilsvarende legitimasjon.

## <a name="connect-to-sftp"></a>Koble til SFTP

1. Gå til **Admin** > **Eksporter mål**.

1. Under **SFTP** velger du **Konfigurer**.

1. Gi målet et gjenkjennelig navn i feltet **Visningsnavn**.

1. Angi et **brukernavn**, et **passord** og et **vertsnavn** og **eksportmappe** for SFTP-kontoen.

1. Velg **Bekreft** for å teste tilkoblingen.

1. Når verifiseringen er vellykket, velger du om du vil eksportere dataene **Komprimert** eller **Pakket ut**, og velger **feltskilletegnet** for de eksporterte filene.

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Neste** for å komme i gang med å konfigurere eksporten.

## <a name="configure-the-export"></a>Konfigurer eksporten

1. Velg enhetene du vil eksportere, for eksempel segmenter.

   > [!NOTE]
   > Hver valgte enhet vil være opptil fem utdatafiler når de eksporteres. 

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).

## <a name="known-limitations"></a>Kjente begrensninger

- Kjøretiden for en eksport avhenger av systemytelsen. Vi anbefaler to CPU-kjerner og 1 GB minne som minimal konfigurasjon av serveren. 
- Det kan ta tre timer å eksportere enheter med opptil 100 millioner kundeprofiler når du bruker den anbefalte minimumskonfigurasjonen av to CPU-kjerner og 1 GB minne. 

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data via SFTP, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at eksportmålet oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]