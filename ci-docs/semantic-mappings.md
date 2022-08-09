---
title: Semantiske tilordninger (forhåndsversjon)
description: Oversikt over semantiske tilordninger og hvordan du bruker dem.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183643"
---
# <a name="semantic-mappings-preview"></a>Semantiske tilordninger (forhåndsversjon)

Med semantiske tilordninger kan du tilordne ikke-aktivitetsdata til forhåndsdefinerte skjemaer. Disse skjemaene hjelper Customer Insights å forstå dataattributtene bedre. Semantisk tilordning og de angitte dataene gir deg ny innsikt og nye funksjoner i Customer Insights. Hvis du vil tilordne aktivitetsdataene til skjemaene, ser du gjennom dokumentasjonen for [aktivitetene](activities.md).

**Semantiske tilordninger er for øyeblikket aktivert for miljøer basert på forretningskontoer**. *ContactProfile* er den eneste typen semantisk tilordning som for øyeblikket er tilgjengelig i Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definere en semantisk enhetstilordning for ContactProfile

1. Gå til **Data** > **Semantiske tilordninger (forhåndsversjon)**.

1. Velg **Legg til semantisk tilordning** for å starte den veiledede opplevelsen.

1. Angi verdiene for følgende felt i **Enhetsdata**-trinnet:

   - **Tilordningsnavn for semantisk enhet**: navn for den semantiske enhetstilordningen.
   - **Kildeenhet**: enhet som inneholder kontaktdata.
   - **Primærnøkkel**: felt som unikt identifiserer en kontaktoppføring. Den skal ikke inneholde duplikat verdier, tomme verdier eller manglende verdier.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Konfigurer den semantiske enhetstilordningen med navn, kildeenhet og primærnøkkel.":::

1. Velg **Neste**.

1. Konfigurer detaljene for å koble kontaktdataene til de tilsvarende forretningsforbindelsesdataene i **Relasjoner**-trinnet. Dette trinnet visualiserer tilkoblingen mellom enheter.  

   Det finnes to typer relasjonsbaner som kan implementeres: **Direkte relasjoner** og **Indirekte relasjoner**. Hvis du vil ha mer informasjon, kan du gå til [direkte og indirekte relasjonsbaner](relationships.md#relationship-paths).

   1. Velg **Legg til relasjon** for å konfigurere relasjonen.
   1. Velg attributtet fra kildeenheten som kobler kontaktenheten til en annen enhet.
   1. Velg enheten du vil koble kontaktenheten til. Velg en enhet fra delen **Forretningsforbindelse-enheter** eller **Mellomliggende enhet**. Hvis du velger en mellomliggende enhet, definerer du en ny relasjon for å koble til målkontoen.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Velg en Forretningsforbindelsesenhet eller en Mellomliggende enhet.":::

   1. Angi et **Relasjonsnavn**. Hvis det allerede finnes en relasjon mellom enhetene, er relasjonsnavnet skrivebeskyttet. Hvis det ikke finnes noen relasjon, opprettes det en ny relasjon med navnet du angir.
   1. Velg **Bruk** for å fullføre relasjonskonfigurasjonen.

   > [!NOTE]
   > Du kan konfigurere flere relasjoner mellom kontaktenheten og andre forretningsforbindelsesenheter med mellomliggende enheter.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisering av ulike relasjoner kobler kontaktenheter til forretningsforbindelsesenheter.":::

1. Velg **Neste**.

1. Velg en **Semantisk type** i trinnet **Angi semantisk type**. Det finnes for øyeblikket én **Semantisk type** som kalles *ContactProfile*.

1. Tilordne kontakt-ID-en til den semantiske *ContactProfile*-typen **Kontakt-ID**. Tilordne eventuelt andre felter, for eksempel fornavn, etternavn, kjønn eller e-post.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Tilordne kontaktdataattributtene til de angitte obligatoriske og valgfrie feltene.":::

1. Velg **Neste**.

1. I trinnet **Se gjennom** ser du gjennom konfigurasjonen av semantisk tilordning. Du kan gjøre endringer ved å velge **Rediger** for den tilsvarende delen.

1. Velg **Lagre**.

1. Velg **Kjør** for å behandle den semantiske tilordningen. Eller velg **Lukk** for å lagre den semantiske tilordningen uten å behandle den. Hvis du vil kjøre den senere, velger du semantisk tilordning og deretter **Oppdater**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Behandle eksisterende semantiske tilordninger

Gå til **Data** > **Semantiske tilordninger (forhåndsversjon)** for å vise lagrede semantiske tilordninger, kildeenheten deres, semantisk type, tilordningstype og status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Alternativer for å behandle semantiske tilordninger.":::

Velg den semantiske tilordningen for å vise tilgjengelige handlinger.
- **Rediger** den gjeldende konfigurasjonen. Velg **Lagre** og **Kjør** for å behandle endringene.
- **Oppdater** den semantiske tilordningen slik at den inneholder de nyeste dataene. Oppdatering av en gitt semantisk tilordning oppdaterer alle semantiske tilordninger av samme type.
- **Gi nytt navn** til den semantiske tilordningen. Velg **Lagre**.
- **Slett** den semantiske tilordningen. Hvis du vil slette flere semantiske tilordninger samtidig, velger du de semantiske tilordningene og sletteikonet. Velg **Slett** for å bekrefte slettingen.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Bruke en semantisk ContactProfile-enhetstilordning til å opprette aktiviteter på kontaktnivå

Når du har opprettet en semantisk enhetstilordning for *ContactProfile*, kan du registrere aktiviteter for kontakter. Den gjør det mulig å se på aktivitetstidslinjen for en forretningsforbindelse hvilken kontakt som var ansvarlig for hver aktivitet. De fleste trinnene følger den vanlige konfigurasjonen av aktivitetstilordninger.

   > [!NOTE]
   > For at aktiviteter på kontaktnivå skal fungere, må du ha både **AccountID**- og **ContactID**-attributtene for hver oppføring for aktivitetsdataene.

1. [Definer en semantisk *ContactProfile*-enhetstilordning](#define-a-contactprofile-semantic-entity-mapping), og kjør den semantiske tilordningen.

1. Gå til **Data** > **Aktiviteter**.

1. Velg **Legg til aktivitet** for å opprette en ny aktivitet.

1. Gi aktiviteten et navn, velg kildeaktivitetsenheten, og velg hovednøkkelen for aktivitetsenheten.

1. I trinnet **Relasjoner** oppretter du en indirekte relasjon mellom aktivitetskildedataene til forretningsforbindelser ved å bruke kontaktdataene som en mellomenhet. Hvis du vil ha mer informasjon, kan du se [direkte og indirekte relasjonsbaner](relationships.md#relationship-paths).
   - Eksempelrelasjon for en aktivitet kalt *Kjøp*:
      - **Aaktivitetsdata for kilde for kjøp** > **Kontakdata** på attributtet **ContactID**
      - **Kontaktdata** > **Data om forretningsforbindelse** på attributtet **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Eksempel på relasjonsoppsett.":::

1. Når du har satt opp Relasjoner, velger du **Neste** og fullfører konfigurasjonen av aktivitetstilordningen. Hvis du vil ha detaljerte trinn for oppretting av aktiviteter, kan du se [definere en aktivitet](activities.md).

1. Kjør aktivitetstilordningene.

1. Etter at en aktivitetstilordning på kontaktnivå har kjørt, velger du **Kunder**. Aktivitetene på kontaktnivå vises på kundetidslinjen.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Endelig resultat etter konfigurasjon av kontaktaktiviteter":::

### <a name="contact-level-activity-timeline-filtering"></a>Tidslinjefiltrering av aktivitet på kontaktnivå

Aktivitetstidslinjen for kundene inkluderer ID-ene eller navnene deres, avhengig av *ContactProfile*-konfigurasjonen for aktivitetene de handlet på. Filtrer aktiviteter etter kontakter på tidslinjen for å se bestemte kontakter du er interessert i. Hvis du vil vise alle aktiviteter som ikke er tilordnet til en bestemt kontakt, velger du **Aktiviteter som ikke er tilordnet til en kontakt**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Filtreringsalternativer som er tilgjengelige for aktiviteter på kontaktnivå.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
