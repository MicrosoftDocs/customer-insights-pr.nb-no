---
title: Eksporter begrensede hendelser
description: Slik eksporterer du begrensede hendelser og basishendelser.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032397"
---
# <a name="export-events"></a>Eksportere hendelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En hendelse representerer brukeratferd. Den registrerer når en bruker viser en side (visningshendelse) eller samhandler med innhold (handlingshendelse). Når du kan bestemme hvilke egenskaper for dataene du vil vise i en rapport, kalles denne virtuelle visningen av dataene for en *begrenset hendelse*. 

- Du kan eksportere hendelser og begrensede hendelser til ekstern lagringsplass. 
- Eksportene er en datastrøm for videresending. Du kan ikke fylle på strømmen. 
- Eksporter har faste skjemaer. Hvis du legger til egendefinerte egenskaper for en hendelse, inkluderes de ikke. Du må opprette en ny eksport.

## <a name="prerequisites"></a>Forutsetninger

Før du konfigurerer en eksport, må du ha tilgang og et aktivt abonnement på Azure Portal. Du trenger informasjon om lagringskontoen under eksportprosessen. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Opprett en Azure Data Lake Storage Gen 2-konto

1. Logg på Azure Portal og [opprett en ny lagringskonto](/azure/storage/common/storage-account-create). 

1. Kontroller at du aktiverer **Hierarkisk navneområde** i fanen **Avansert**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Aktiver hierarkisk navneområde på fanen avansert.":::

1. Når den er distribuert, går du til den nyopprettede lagringskontoen. Velg **Innstillinger** > **Tilgangsnøkler** i navigasjonsruten. 

1. Kopier **kontonavnet** og **nøkkelen** for å bruke dem når du oppretter en ny eksport.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Tilgangsnøkler i en lagringskonto.":::

## <a name="export-events"></a>Eksporter hendelser

Du kan eksportere hendelser på to ulike måter: 
- Gå til **Data** > **Eksporter** og velg **Ny eksport**.
- Gå til **Data** > **Hendelser**, velg **Mer [...]** ved siden av hendelsen du vil eksportere, og velg **Eksporter** på rullegardinmenyen. 

Du får veiledning for hvordan du oppretter en eksport:

1. Oppgi et **eksportnavn**.

1. Velg nedtrekkslisten **Valg av hendelser**, velg basishendelser og begrensede hendelser for inkludere i eksporten. 

1. Under **Filstruktur** velger du frekvensen for å opprette nye filer i mållagringen. Hendelser eksporteres fortløpende etter hvert som de kommer.

1. Velg formatet for eksporten. Du kan velge mellom formatene **Common Data Model**, **CSV** og **JSON**. Hvis du vil bruke eksporten med andre Dynamics 365-programmer, anbefaler vi at du bruker Common Data Model-formatet.

1. Angi Azure Data Lake Storage Gen 2-plasseringen i trinnet **Velg mål**.
    1. **ADLS Gen 2-kontonavn** er navnet på lagringskontoen du vil lagre eksporten til. 
    1. **Mappebanen** definerer hvor eksporten skal lagres i filsystemet og mappestrukturen til lagringskontoen.
    1. **Delt nøkkel** er tilgjengelig fra Azure Portal for lagringskontoen.

1. Se gjennom og bekreft valgene.

## <a name="view-and-manage-exports"></a>Vis og administrer eksporter

Når du har konfigurert en eksport, går du til **Data** > **Eksporter** for å vise den. Velg **Mer [...]** for en eksisterende eksport for å redigere eller slette den.


[!INCLUDE[footer-include](../includes/footer-banner.md)]