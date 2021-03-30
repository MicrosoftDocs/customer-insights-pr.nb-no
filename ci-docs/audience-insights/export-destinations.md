---
title: Eksportmål
description: Eksporter data og administrer eksportmål.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596097"
---
# <a name="export-destinations-preview-overview"></a>Oversikt over eksportmål (forhåndsversjon)

Siden **Eksportmål** viser alle stedene du har konfigurert til å eksportere data til. Du kan også legge til nye mål for eksport. I tillegg vises det tilgjengelige alternativer for eksport. Få en rask oversikt og en beskrivelse, og finn ut hva du kan gjøre med hvert utvidelsesalternativ. Eksporter samlede profiler, mål og segmenter til apper som støttes for virksomheten din.

Gå til **Admin** > **Eksportmål** for å finne følgende utvidelsesalternativer:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe Experience Platform](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Azure Blob Storage](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Robot for Microsoft Teams](export-teams-bot.md)
- [Customer Insights-API](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (kundekorttillegg)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Salgssenter (kundekorttillegg)](customer-card-add-in.md)
- [Facebook-annonseadministrasjon](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

## <a name="add-a-new-export-destination"></a>Legge til et nytt eksportmål

Hvis du vil legge til eksportmål, må du ha [administratortillatelser](permissions.md). Hvis du eksporterer til Microsoft-tjenester, antas det at begge tjenestene er i samme organisasjon.

1. Gå til **Admin** > **Eksporter mål**.

1. Bytt til kategorien **Mine eksportmål**.

1. Velg **Legg til mål** for å opprette et nytt eksportmål.

1. I ruten **Legg til mål** velger du **Type** eksportmål i rullegardinlisten.

1. Angi de nødvendige detaljene, og velg deretter **Neste** for å opprette eksportmålet.

Du kan også velge **Konfigurer** på en flis i kategorien **Oppdag**.

## <a name="view-export-destinations"></a>Vise eksportmål

Når du har opprettet eksportmålene, finner du dem i en tabell i kategorien **Mine eksportmål**. Denne tabellen har tre kolonner:

- **Visningsnavn**: Navnet du angav da du opprettet målet.
- **Type**: Typen eksportmål du angir når du oppretter målet.
- **Opprettet**: Datoen du opprettet målet.

## <a name="edit-an-export-destination"></a>Redigere et eksportmål

1. Velg den loddrette ellipsen for eksportmålet du vil redigere.

   > [!div class="mx-imgBorder"]
   > ![Loddrett ellipse](media/export-destinations-page-ellipsis.png "Loddrett ellipse")

1. Velg **Rediger** på rullegardinmenyen.

1. Endre verdiene som krever oppdatering, og velg **Lagre**.

## <a name="export-data-on-demand"></a>Eksportere data etter behov

Når du har konfigurert en kobling for et eksportmål, kjøres eksporter med alle [planlagte oppdateringer](system.md#schedule-tab).

Hvis du vil eksportere data uten å vente på en planlagt oppdatering, kan du gå til kategorien **Mine eksportmål** på **Administrator** > **Eksportmål**.

> [!div class="mx-imgBorder"]
> ![Loddrett ellipse](media/export-destinations-page-ellipsis.png "Loddrett ellipse")

- Velg **Eksporter** over listen for å kjøre eksporten til alle eksportmålene samtidig.
- Velg ellipsen (...) etter et listeelement, og velg deretter **Eksporter**-alternativet for å kjøre eksporten for et enkelt eksportmål.

## <a name="remove-an-export-destination"></a>Fjerne et eksportmål

Hvis du vil fjerne et eksportmål, starter du fra hovedsiden for **Eksportmål**.

1. Velg den loddrette ellipsen for eksportmålet du vil fjerne.

   > [!div class="mx-imgBorder"]
   > ![Loddrett ellipse](media/export-destinations-page-ellipsis.png "Loddrett ellipse")

2. Velg **Fjern** fra rullegardinmenyen.

3. Bekreft fjerningen ved å velge **Fjern** i bekreftelsesdialogboksen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]