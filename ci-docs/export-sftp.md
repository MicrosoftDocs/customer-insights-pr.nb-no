---
title: Eksportere data til SFTP-verter (forhåndsversjon) (inneholder video)
description: Lær hvordan du konfigurerer tilkoblingen og eksporterer til en SFTP-plassering.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207241"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Eksporter data til SFTP-verter (forhåndsversjon)

Bruk kundedataene i tredjepartsprogrammer ved å eksportere dem til en plassering i Secure File Transfer Protocol (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Forutsetning

- Tilgjengelighet av en SFTP-vert og tilsvarende legitimasjon.

## <a name="known-limitations"></a>Kjente begrensninger

- SFTP-mål bak brannmurer støttes for øyeblikket ikke.
- Kjøretiden for en eksport avhenger av systemytelsen. Vi anbefaler to CPU-kjerner og 1 GB minne som minimal konfigurasjon av serveren.
- Opptil 100 millioner kundeprofiler, som kan ta 90 minutter når du bruker den anbefalte minimumskonfigurasjonen av to CPU-kjerner og 1 GB minne.
- Hvis du bruker en SSH-nøkkel til autentisering, kontrollerer du at du [oppretter den private nøkkelen](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) i PEM- eller SSH.COM-format. Hvis du bruker Putty, konverterer du den private nøkkelen ved å eksportere den som Open SSH. Følgende privatnøkkelformater støttes:
  - RSA i formatene OpenSSL PEM og ssh.com
  - DSA i formatene OpenSSL PEM og ssh.com
  - ECDSA 256/384/521 i formatet OpenSSL PEM
  - ED25519 og RSA i nøkkelformatet OpenSSH

## <a name="set-up-connection-to-sftp"></a>Konfigurer tilkobling til SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Tilkoblinger**.

1. Velg **Legg til tilkobling**, og velg **SFTP**.

1. Gi tilkoblingen et gjenkjennelig navn i **Visningsnavn**-feltet. Navnet og tilkoblingstypen beskriver denne tilkoblingen. Vi anbefaler at du velger et navn som forklarer formålet med og målet for tilkoblingen.

1. Velg hvem som kan bruke denne tilkoblingen. Som standard er det bare administratorer. Hvis du vil ha mer informasjon, se [Tillate bidragsytere å bruke en tilkobling for eksporter](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Velg om du vil autentisere via SSH eller brukernavn/passord for tilkoblingen, og oppgi de nødvendige detaljene. Hvis du bruker en SSH-nøkkel til autentisering, kontrollerer du at du [oppretter den private nøkkelen](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) i PEM- eller SSH.COM-format. Hvis du bruker Putty, konverterer du den private nøkkelen ved å eksportere den som Open SSH. Følgende privatnøkkelformater støttes:
   - RSA i formatene OpenSSL PEM og ssh.com
   - DSA i formatene OpenSSL PEM og ssh.com
   - ECDSA 256/384/521 i formatet OpenSSL PEM
   - ED25519 og RSA i nøkkelformatet OpenSSH

1. Velg **Bekreft** for å teste tilkoblingen.

1. Se gjennom [datapersonvern og -samsvar](connections.md#data-privacy-and-compliance), og velg **Jeg godtar**.

1. Velg **Lagre** for å fullføre tilkoblingen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksporter**.

1. Velg **Legg til eksport**.

1. Velg en tilkobling fra SFTP-delen i feltet **Tilkobling for eksport**. Kontakt en administrator hvis ingen tilkobling er tilgjengelig.

1. Skriv inn et navn for eksporten.

1. Velg om du vil eksportere dataene **Komprimert** eller **Pakket ut** og **feltskilletegnet** for de eksporterte filene.

1. Velg enhetene du vil eksportere, for eksempel segmenter.

   > [!NOTE]
   > Hver valgte enhet blir delt opp i maks. fem utdatafiler når de eksporteres.

1. Velg **Lagre**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Eksport av enheter som inneholder store mengder data, kan føre til flere CSV-filer i samme mappe for hver eksport. Oppdeling av eksporter skjer av ytelsesårsaker for å redusere tiden det tar før en eksport fullføres.

[!INCLUDE [footer-include](includes/footer-banner.md)]
