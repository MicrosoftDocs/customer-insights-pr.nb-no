---
title: Eksportere Customer Insights-data til SFTP-verter
description: Lær hvordan du konfigurerer tilkoblingen til en SFTP-vert.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643515"
---
# <a name="connector-for-sftp-preview"></a>Kobling for SFTP (forhåndsversjon)

Bruk kundedata i tredjepartsprogrammer ved å eksportere dem til en SFTP-vert (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Forutsetninger

- Tilgjengelighet av en SFTP-vert og tilhørende legitimasjoner.

## <a name="connect-to-sftp"></a>Koble til SFTP

1. Gå til **Admin** > **Eksporter mål**.

1. Under **SFTP** velger du **Konfigurer**.

1. Gi målet et gjenkjennelig navn i feltet **Visningsnavn**.

1. Angi et **brukernavn**, et **passord** og et **vertsnavn** for SFTP-kontoen. Eksempel: Hvis rotmappen til SFTP-serveren er /root/folder, og du ønsker at dataene skal eksporteres til /root/folder/ci_export_destination_folder, må verten være sftp://<server_address>/ci_export_destination_folder".

1. Velg **Bekreft** for å teste tilkoblingen.

1. Når bekreftelsen er vellykket, velger du om du vil eksportere dataene **zippet** eller **utpakket**, og deretter velger du **feltskilletegnet** for de eksporterte filene.

1. Velg **Jeg godtar** for å bekrefte **Datapersonvern og -samsvar**.

1. Velg **Neste** for å komme i gang med å konfigurere eksporten.

## <a name="configure-the-connection"></a>Konfigurere tilkoblingen

1. Velg **kundeattributtene** du vil eksportere. Du kan eksportere ett eller flere attributter.

1. Velg **Neste**.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

## <a name="export-the-data"></a>Eksportere dataene

Du kan [eksportere data etter behov](export-destinations.md). Eksporten blir også kjørt med hver [planlagte oppdatering](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Datapersonvern og -samsvar

Når du aktiverer Dynamics 365 Customer Insights for overføring av data via SFTP, tillater du overføring av data utenfor samsvarsgrensen for Dynamics 365 Customer Insights, inkludert potensielt sensitive data, for eksempel personlige data. Microsoft overfører slike data etter instruksjon fra deg, men du er ansvarlig for å sørge for at eksportmålet oppfyller alle forpliktelser til personvern eller sikkerhet du måtte ha. Hvis du vil ha mer informasjon, kan du se [Microsofts personvernerklæring](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights-administratoren kan fjerne dette eksportmålet når som helst for å slutte å bruke denne funksjonaliteten.
