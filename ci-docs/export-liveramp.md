---
title: Eksportere segmenter til LiveRamp (forhåndsvisning)
description: Lær hvordan du konfigurerer tilkoblingen og eksporten til LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196728"
---
# <a name="export-segments-to-liverampreg-preview"></a>Eksportere segmenter til LiveRamp&reg; (forhåndsvisning)

Aktiver dataene i LiveRamp for å koble til over 500 plattformer på tvers av digitale og sosiale systemer og TV-er. Du kan arbeide med dataene dine i LiveRamp for å målrette, undertrykke og tilpasse annonsekampanjer.

## <a name="prerequisites"></a>Forutsetning

- Et LiveRamp-abonnement for å bruke denne koblingen. Hvis du vil ha et abonnement, [kontakter du LiveRamp](https://liveramp.com/contact/) direkte. [Finn ut mer om LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Kjente begrensninger

- LiveRamp-eksporten bruker en SFTP-eksport. SFTP-mål bak brannmurer støttes for øyeblikket ikke.
- Hvis du bruker en SSH-nøkkel til autentisering, kontrollerer du at du [oppretter den private nøkkelen](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) i PEM- eller SSH.COM-format. Hvis du bruker Putty, konverterer du den private nøkkelen ved å eksportere den som Open SSH. Følgende privatnøkkelformater støttes:
  - RSA i formatene OpenSSL PEM og ssh.com
  - DSA i formatene OpenSSL PEM og ssh.com
  - ECDSA 256/384/521 i formatet OpenSSL PEM
  - ED25519 og RSA i nøkkelformatet OpenSSH
- Kjøretiden for en eksport avhenger av systemytelsen. Vi anbefaler to CPU-kjerner og 1 GB minne som minimal konfigurasjon av serveren.
- Det kan ta tre timer å eksportere enheter med opptil 100 millioner kundeprofiler når du bruker den anbefalte minimumskonfigurasjonen av to CPU-kjerner og 1 GB minne.
- Faktisk antall profiler (eller mengde data) du kan eksportere til LiveRamp, avhenger av LiveRamp-abonnementet.

## <a name="set-up-connection-to-liveramp"></a>Konfigurere tilkobling til LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **LiveRamp**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg om du vil autentisere via SSH eller brukernavn/passord for tilkoblingen, og oppgi de nødvendige detaljene.

1. Velg **Bekreft** for å teste tilkoblingen til LiveRamp.

1. Etter vellykket verifisering, ser du gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance) og velger **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra LiveRamp-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. I feltet **Koble til data** velger du **E-post**, **Navn og adresse** eller **Telefon** for å sende til LiveRamp for identitetsløsning.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="LiveRamp-kobling med attributtilordning.":::

1. Tilordne de tilsvarende attributtene fra *Kunde*-enheten for den valgte nøkkel-IDen.

1. Velg **Legg til attributt** for å tilordne flere attributter som skal sendes til LiveRamp.

   > [!TIP]
   > Det å sende flere nøkkelidentifikatorattributter til LiveRamp gir deg sannsynligvis en høyere samsvarsrate.

1. Velg segmentene du vil eksportere.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
