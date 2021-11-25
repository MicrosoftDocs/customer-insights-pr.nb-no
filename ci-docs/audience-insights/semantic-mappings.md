---
title: Semantiske tilordninger (forhåndsversjon)
description: Oversikt over semantiske tilordninger og hvordan du bruker dem.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: f23c622572ff9f967eca07de7898419d1ffc18b0
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731955"
---
# <a name="semantic-mappings"></a>Semantiske tilordninger

Med semantiske tilordninger kan du tilordne ikke-aktivitetsdata til forhåndsdefinerte skjemaer. Disse skjemaene hjelper målgruppeinnsikt med å forstå dataattributtene bedre. Semantisk tilordning og de angitte dataene gir deg ny innsikt og nye funksjoner i målgruppeinnsikt. Hvis du vil tilordne aktivitetsdataene til skjemaene, ser du gjennom dokumentasjonen for [aktivitetene](activities.md).

**Semantiske tilordninger er for øyeblikket aktivert for miljøer basert på forretningskontoer**. *ContactProfile* er den eneste typen semantisk tilordning som for øyeblikket er tilgjengelig i målgruppeinnsikt.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definere en semantisk enhetstilordning for ContactProfile

1. I målgruppeinnsikt går du til **Data** > **Semantiske tilordninger (forhåndsversjon)**.

1. Velg **Legg til semantisk tilordning** for å starte den veiledede opplevelsen.

1. Angi verdiene for følgende felt i **Enhetsdata**-trinnet:

   - **Tilordningsnavn for semantisk enhet**: Angi et navn for den semantiske enhetstilordningen.
   - **Kildeenhet**: Velg en enhet som inneholder kontaktdata.
   - **Primærnøkkel**: Velg feltet som unikt identifiserer en kontaktoppføring. Den skal ikke inneholde duplikat verdier, tomme verdier eller manglende verdier.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Konfigurer den semantiske enhetstilordningen med navn, kildeenhet og primærnøkkel.":::

1. Velg **Neste** for å fortsette.

1. Konfigurer detaljene for å koble kontaktdataene til de tilsvarende forretningsforbindelsesdataene i **Relasjoner**-trinnet. Dette trinnet visualiserer tilkoblingen mellom enheter.  

   Det finnes to typer relasjonsbaner som kan implementeres: **Direkte relasjoner** og **Indirekte relasjoner**. Hvis du vil ha mer informasjon, kan du gå til [direkte og indirekte relasjonsbaner](relationships.md#relationship-paths).

   1. Velg **Legg til relasjon** for å konfigurere relasjonen.
   1. Velg attributtet fra kildeenheten som kobler kontaktenheten til en annen enhet.
   1. Velg enheten du vil koble kontaktenheten til. Du kan velge en enhet fra delen **Forretningsforbindelse-enheter** eller **Mellomliggende enhet**. Hvis du velger en mellomliggende enhet, må du definere en ny relasjon for å koble til målkontoen.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Velg en Forretningsforbindelsesenhet eller en Mellomliggende enhet.":::

   1. Angi et **Relasjonsnavn**. Hvis det allerede finnes en relasjon mellom enhetene, er relasjonsnavnet skrivebeskyttet. Hvis det ikke finnes noen relasjon, opprettes det en ny relasjon med navnet du angir.
   1. Velg **Bruk** for å fullføre relasjonskonfigurasjonen.

   > [!NOTE]
   > Du kan konfigurere flere relasjoner mellom kontaktenheten og andre forretningsforbindelsesenheter med mellomliggende enheter.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisering av ulike relasjoner kobler kontaktenheter til forretningsforbindelsesenheter.":::

1. Velg **Neste** når du er ferdig med relasjonskonfigurasjonen.

1. Velg en **Semantisk type** i trinnet **Angi semantisk type**. Det finnes for øyeblikket én **Semantisk type** som kalles *ContactProfile*.

1. Tilordne dataene til *ContactProfile* **Semantisk type** for feltene som vises.
   - Obligatorisk felt: Kontakt-ID
   - Valgfrie felt: ornavn, etternavn, fødselsdato, kjønn, primær e-post og primær telefon

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Tilordne kontaktdataattributtene til de angitte obligatoriske og valgfrie feltene.":::

1. Velg **Neste** for å fortsette.

1. I trinnet **Se gjennom** tar du en titt på konfigurasjonen av semantisk tilordning. Velg **Rediger** for den tilsvarende delen for å gjøre endringer.

1. Velg **Lagre** for å lagre den nye **Semantiske tilordningen**.

1. Når du har lagret, kan du velge **Kjør** prosess for semantisk tilordning, eller du kan velge **Lukk** for å lagre den semantiske tilordningen uten å behandle den.

1. Hvis du vil kjøre en semantisk tilordning senere, velger du semantisk tilordning og velger **Oppdater**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Behandle eksisterende semantiske tilordninger

På **Data** > **Semantiske tilordninger (forhåndsversjon)** kan du vise alle lagrede semantiske tilordninger og administrere dem. Hver semantisk tilordning representeres av en separat rad. Du finner detaljer om kildeenheten, semantisk type, tilordningstype og statusen.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Alternativer for å behandle semantiske tilordninger.":::

- **Rediger**: Åpner konfigurasjonen for det semantiske tilordningsoppsettet i gjennomgangstrinnet. Du kan endre gjeldende konfigurasjon. Velg **Lagre** og **Kjør** for å behandle endringene.

- **Oppdater**: Oppdaterer den valgte semantiske tilordningen med de mest oppdaterte dataene fra enhetene som er en del av konfigurasjonen. Oppdatering av en gitt semantisk tilordning oppdaterer alle semantiske tilordninger av samme type.

- **Gi nytt navn**: Åpner en dialogboks der du kan angi et annet navn for den valgte semantiske tilordningen. Velg **Lagre** for å ta i bruk endringene.

- **Slett:** Åpner en dialogboks for å bekrefte slettingen av den valgte semantiske tilordningen. Du kan også slette mer enn én semantisk tilordning samtidig ved å velge semantiske tilordninger og sletteikonet. Velg **Slett** for å bekrefte slettingen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
