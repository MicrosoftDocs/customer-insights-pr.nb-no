---
title: Semantiske tilordninger (forhåndsversjon)
description: Oversikt over semantiske tilordninger og hvordan du bruker dem.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881842"
---
# <a name="semantic-mappings-preview"></a>Semantiske tilordninger (forhåndsversjon)

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

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Bruke en semantisk ContactProfile-enhetstilordning til å opprette aktiviteter på kontaktnivå

Når du har opprettet en semantisk enhetstilordning for *ContactProfile*, kan du registrere aktiviteter for kontakter. Den gjør det mulig å se på aktivitetstidslinjen for en forretningsforbindelse hvilken kontakt som var ansvarlig for hver aktivitet. De fleste trinnene følger den vanlige konfigurasjonen av aktivitetstilordninger.

   > [!NOTE]
   > For at aktiviteter på kontaktnivå skal fungere, må du ha både **AccountID**- og **ContactID**-attributtene for hver oppføring for aktivitetsdataene.

1. [Definere en *ContactProfile*-semantisk enhetstilordning.](#define-a-contactprofile-semantic-entity-mapping) og kjøre den semantiske tilordningen.

1. I Målgruppeinnsikt går du til **Data** > **Aktiviteter**.

1. Velg **Legg til aktivitet** for å opprette en ny aktivitet.

1. Gi aktiviteten et navn, velg kildeaktivitetsenheten, og velg hovednøkkelen for aktivitetsenheten.

1. I trinnet **Relasjoner** oppretter du en indirekte relasjon mellom aktivitetskildedataene til forretningsforbindelser ved å bruke kontaktdataene som en mellomenhet. Hvis du vil ha mer informasjon, kan du se [direkte og indirekte relasjonsbaner](relationships.md#relationship-paths).
   - Eksempelrelasjon for en aktivitet kalt *Kjøp*:
      - **Aaktivitetsdata for kilde for kjøp** > **Kontakdata** på attributtet **ContactID**
      - **Kontaktdata** > **Data om forretningsforbindelse** på attributtet **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Eksempel på relasjonsoppsett.":::

1. Når du har satt opp Relasjoner, velger du **Neste** og fullfører konfigurasjonen av aktivitetstilordningen. Hvis du vil ha detaljerte trinn for oppretting av aktiviteter, kan du se [definere en aktivitet](activities.md).

1. Kjør aktivitetstilordningene.

1. Aktivitetene på kontaktnivå vil nå være synlige på tidslinjen for kunden.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Endelig resultat etter konfigurasjon av kontaktaktiviteter":::

### <a name="contact-level-activity-timeline-filtering"></a>Tidslinjefiltrering av aktivitet på kontaktnivå

Når du har konfigurert en aktivitetstilordning på kontaktnivå og kjørt den, oppdateres tidslinjen for aktiviteten for kundene. Den inkluderer IDer eller navn, avhengig av *ContactProfile*-konfigurasjonen, for aktivitetene de handlet på. Du kan filtrere aktiviteter etter kontakter på tidslinjen for å se bestemte kontakter du er interessert i. I tillegg kan du vise alle aktiviteter som ikke er tilordnet til en bestemt kontakt, ved å velge **Aktiviteter som ikke er tilordnet til en kontakt**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Filtreringsalternativer som er tilgjengelige for aktiviteter på kontaktnivå.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
