---
title: Eksportere Customer Insights-data til Dynamics 365 Sales
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d8a35424f4271b350b8d84e72a01deb6d69652a0
ms.sourcegitcommit: 08a5dfcc4f9d293c8e7ac4fef604bc52985b1b78
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/04/2022
ms.locfileid: "8090935"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Bruke segmenter i Dynamics 365 Sales (forhåndsversjon)



Bruk kundedata til å opprette markedsføringslister, oppfølgingsarbeidsflyter og sende ut kampanjer med Dynamics 365 Sales.

## <a name="known-limitations"></a>Kjente begrensninger

- Eksporter til Dynamics 365 Sales er begrenset til 100 000 medlemmer per segment.
- Det kan ta opptil 3 timer å fullføre segmenteksporter til Dynamics 365 Sales. 

## <a name="prerequisite-for-connection"></a>Forutsetninger for en tilkobling

1. Kontaktoppføringer må finnes i Dynamics 365 Sales før du kan eksportere et segment fra Customer Insights til Sales. Les mer om hvordan du inntar kontakter i [Dynamics 365 Sales ved hjelp av Microsoft Dataverse](connect-power-query.md).

   > [!NOTE]
   > Hvis du eksporterer segmenter fra målgruppeinnsikt til Sales, opprettes ikke nye kontaktoppføringer i Sales-forekomstene. Kontaktoppføringene fra Sales må legges inn i målgruppeinnsikt og brukes som en datakilde. De må også inkluderes i den samlede kundeenhet for å tilordne kunde-ID-er til kontakt-ID-er før segmenter kan eksporteres.

## <a name="set-up-the-connection-to-sales"></a>Konfigurer tilkoblingen til Sales

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **Dynamics 365 Sales** for å konfigurere tilkoblingen.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Hvis du ikke gjør noe, vil standarden være Administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Skriv inn organisasjonens URL-adresse for Sales i **Serveradresse**-feltet.

1. I delen **Serveradministratorkonto** velger du **Logg på** og velger en Dynamics 365 Sales-konto.

1. Tilordne et kunde-ID-felt til Dynamics 365-kontakt-ID-en.

1. Velg **Lagre** for å fullføre tilkoblingen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksporten hvis du har tilgang til en tilkobling av denne typen. Hvis du vil ha mer informasjon, se [Tillatelser som kreves for å konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til mål** for å opprette en ny eksport.

1. Velg en tilkobling fra Dynamics 365 Sales-delen i feltet **Tilkobling for eksport**. Hvis du ikke ser dette inndelingsnavnet, er ingen tilkoblinger av denne typen tilgjengelige for deg.

1. Velg ett eller flere segmenter.

1. Velg **Lagre**

Hvis du lagrer en eksport, kjøres ikke eksporten umiddelbart.

Eksporten kjører med hver [planlagte oppdatering](system.md#schedule-tab). Du kan også [eksportere data ved behov](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
