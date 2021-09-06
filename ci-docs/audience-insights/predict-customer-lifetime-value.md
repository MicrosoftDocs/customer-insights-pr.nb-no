---
title: Prediksjon av verdi for kundelevetid (CLV)
description: Forutsi omsetningspotensialet for aktive kunder i fremtiden.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 740d6a5a749e156414b0e80193334051b7f2632fe4d1f4291d74b99250f35bc2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035381"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Prediksjon av verdi for kundelevetid (CLV) (forhåndsversjon)

Forutsi potensiell verdi (omsetning) som individuelle aktive kunder kommer til å innføre i virksomheten i løpet av en definert fremtidig tidsperiode. Denne funksjonen kan hjelpe deg med å oppnå ulike mål: 
- Identifisere verdifulle kunder og behandle denne innsikten
- Opprette strategiske kundesegmenter basert på potensiell verdi for å kjøre tilpassede kampanjer med målrettet innsats for salg, markedsføring og støtte
- Veilede produktutvikling ved å fokusere på funksjoner som øker kundeverdien
- Optimalisere salgs- eller markedsføringsstrategi og tildele budsjett mer nøyaktig for kundesalg
- Gjenkjenne og belønne kunder med høy verdi gjennom lojalitetsprogrammer eller belønningsprogrammer 

## <a name="prerequisites"></a>Forutsetninger

Før du kommer i gang, må du reflektere hva CLV betyr for virksomheten. For øyeblikket støtter vi transaksjonsbasert CLV-prediksjon. Den beregnede verdien for en kunde er basert på loggen over forretningstransaksjoner. Hvis du vil opprette prediksjonen, trenger du minst [bidragsytertilltaelser](permissions.md).

Siden det ikke tar lang tid å konfigurere og kjøre en CLV-modell, bør du vurdere å opprette flere modeller med varierende inndatainnstillinger og sammenligne modellresultater for å se hvilket modellscenario som passer best til dine forretningsbehov.

###  <a name="data-requirements"></a>Datakrav

Følgende data er obligatoriske, og der det er merket som valgfritt, anbefales det for økt modellytelse. Jo flere data modellen kan behandle, jo mer nøyaktig blir prediksjonen. Vi anbefaler derfor at du tar inn flere kundeaktivitetsdata hvis disse er tilgjengelige.

- Kundeidentifikator: unik identifikator for å samsvare transaksjoner med en individuell kunde

- Transaksjonslogg: logg over historiske transaksjoner med semantisk dataskjema
    - **Transaksjons-ID**: unik identifikator for hver transaksjon
    - **Transaksjonsdato**: dato, helst et tidsstempel for hver transaksjon
    - **Transaksjonsbeløp**: pengeverdi (for eksempel omsetning eller fortjenestemargin) for hver transaksjon
    - **Etikett tilordnet til returer** (valgfritt): boolsk verdi som angir om transaksjonen er en retur 
    - **Produkt-ID** (valgfritt): produkt-ID for produktet involvert i transaksjonen

- Tilleggsdata (valgfritt), for eksempel
    - Nettaktiviteter: logg for nettstedsbesøk, e-postlogg
    - Lojalitetsaktiviteter: avsetning av lojalitetspoeng og innløsningslogg
    - Kundeservicelogg, servicesamtale, klage eller returhistorikk
- Data om kundeaktiviteter (valgfritt):
    - Aktivitets-ID-er for å skille mellom aktiviteter av samme type
    - Kunde-ID-er for å tilordne aktiviteter til kundene
    - Aktivitetsinformasjon som inneholder navnet på og datoen for aktiviteten
    - Det semantiske dataskjemaet for aktiviteter omfatter følgende: 
        - **Primærnøkkel**: En unik identifikator for en aktivitet
        - **Tidsstempel**: Dato og klokkeslett for hendelsen som er identifisert ved hjelp av primærnøkkelen
        - **Hendelse (aktivitetsnavn)**: Navnet på hendelsen du vil bruke
        - **Detaljer (beløp eller verdi)**: Detaljer om kundeaktiviteten

- Kjennetegn for foreslåtte data:
    - Tilstrekkelige historiske data: minst ett år med transaksjonsdata. Helst to til tre år med transaksjonsdata for å forutsi CLV i ett år.
    - Flere kjøp per kunde: Ideelt sett minst to til tre transaksjoner per kunde-ID, helst på flere datoer.
    - Antall kunder: Minst 100 unike kunder, helst mer enn 10 000 kunder. Modellen vil mislykkes med færre enn 100 kunder og utilstrekkelige historiske data
    - Datafullstendighet: Mindre enn 20 % mangler verdier i obligatoriske felter i inndataene   

> [!NOTE]
> - Modellen krever kundenes transaksjonshistorikk. Bare én transaksjonsloggenhet kan konfigureres for øyeblikket. Hvis det er flere innkjøps-/transaksjonsenheter, kan du slå dem sammen i Power Query før datainntak.
> - For flere kundeaktivitetsdata (valgfritt) kan du imidlertid legge til så mange kundeaktivitetsenheter som du vil ta hensyn til etter modellen.

## <a name="create-a-customer-lifetime-value-prediction"></a>Opprett en prediksjon av verdi for kundelevetid

1. I Målgruppeinnsikt går du til **Intelligens** > **Prognoser**.

1. Velg flisen **Verdi for kundelevetid** og velg **Bruk modell**. 

1. Velg **Komme i gang** i ruten **Verdi for kundelevetid (forhåndsversjon)**.

1. **Gi navn til denne modellen** og **Navn på utdataenheten** for å skille dem fra andre modeller eller enheter.

1. Velg **Neste**.

### <a name="define-model-preferences"></a>Definer modellinnstillinger

1. Angi en **prediksjonstidsperiode** for å definere hvor langt inn i fremtiden du vil forutsi CLV.    
   Enheten angis som standard som måneder. Du kan endre den til år for å se lenger inn i fremtiden.

   > [!TIP]
   > For å kunne forutsi CLV nøyaktig for tidsperioden du angir, trenger du en sammenlignbar periode med historiske data. Hvis du for eksempel vil forutsi CLV for de neste 12 månedene, anbefales det at du har minst 18–24 måneder med historiske data.

1. Angi hva **aktive kunder** betyr for virksomheten. Angi tidsramme der en kunde må ha hatt minst én transaksjon for å bli betraktet som aktiv. Modellen vil bare forutsi CLV for aktive kunder. 
   - **La modellen beregne innkjøpsintervall (anbefales)**: Modellen analyserer dataene og bestemmer en tidsperiode basert på historiske kjøp.
   - **Angi intervallet manuelt**: Hvis du har en bestemt forretningsdefinisjon for en aktiv kunde, velger du dette alternativet og angir tidsperioden i henhold til dette.

1. Definer persentil av **kunde med høy verdi** for å aktivere modellen for å gi resultater som passer til forretningsdefinisjonen.
    - **Modellberegning (anbefales)**: Modellen analyserer dataene dine og avgjør hva en kunde med høy verdi kan være for virksomheten basert på kundenes transaksjonshistorikk. Modellen bruker en heurisk regel (inspirert av 80/20-regelen eller pareto-prinsippene) for å finne andelen av kunder med høy verdi. Prosentandel av kunder som bidro til 80 % akkumulert omsetning for virksomheten i den historiske perioden, regnes som kunder med høy verdi. Vanligvis bidrar mindre enn 30–40 % kunder til 80 % akkumulert omsetning. Dette antallet kan imidlertid variere avhengig av virksomheten og bransjen.    
    - **Prosent av de mest aktive kundene**: Definer kunder med høy verdi for virksomheten som en persentil av de mest aktive, betalende kundene. Du kan for eksempel bruke dette alternativet til å definere gode kunder som topp 20 % av fremtidige betalende kunder.

    Hvis virksomheten din definerer kunder med høy verdi på en annen måte, må du [gi oss beskjed for det vil vi gjerne høre om](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Velg **Neste** for å fortsette til neste trinn.

### <a name="add-required-data"></a>Legg til obligatoriske data

1. I trinnet **Obligatoriske data** velger du **Legg til data** for **Historikk for kundetransaksjon**, og velg enheten som inneholder informasjon om transaksjonshistorikken, slik dette er beskrevet i [forhåndskravene](#prerequisites).

1. Tilordne de semantiske feltene til attributter i kjøpsloggenheten, og velg deretter **Neste**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Bilde av konfigurasjonstrinnet for å tilordne dataattributter for obligatoriske data.":::
 
1. Hvis feltene nedenfor ikke fylles ut, konfigurerer du relasjonen fra kjøpshistorikkenheten til *kundeenheten* og velger **Lagre**.
    1. Velg transaksjonshistorikkenheten.
    1. Velg feltet som identifiserer en kunde i kjøpshistorikkenheten. Det må relateres til den primære kunde-ID-en til kundeenheten.
    1. Velg enheten som samsvarer med den primære kundeenheten.
    1. Angi et navn som beskriver relasjonen.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Bilde av konfigurasjonstrinn for å definere relasjonen med kundeenheten.":::

1. Velg **Neste**.

### <a name="add-optional-data"></a>Legg til valgfrie data

Data som gjenspeiler viktige samhandlinger med kunder (for eksempel nett, kundeservice og hendelseslogger), legger til kontekst i transaksjonsoppføringer. Flere mønstre som finnes i kundeaktivitetsdataene, kan forbedre nøyaktigheten av prediksjonene. 

1. Velg **Legg til data** i trinnet **Tilleggsdata (valgfritt)**. Velg kundeaktivitetsenheten som inneholder informasjon om kundeaktiviteten, slik det er beskrevet i [forhåndskravene](#prerequisites).

1. Tilordne de semantiske feltene til attributter i kundeaktivitetsenheten, og velg deretter **Neste**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Bilde av konfigurasjonstrinnet for å tilordne felter for tilleggsdata.":::

1. Velg en aktivitetstype som samsvarer med typen kundeaktivitet du legger til. Velg blant eksisterende aktivitetstyper, eller legg til en ny aktivitetstype.

1. Konfigurer relasjonen fra kundeaktivitetsenheten til *kundeenheten*.
    
    1. Velg feltet som identifiserer kunden i kundeaktivitetstabellen. Den kan være direkte relatert til den primære kunde-ID-en til *kundeenheten*.
    1. Velg *kundeenheten* som samsvarer med den primære *kundeenheten*.
    1. Angi et navn som beskriver relasjonen.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Bilde av trinnet i konfigurasjonsflyten for å legge til tilleggsdata og konfigurere aktiviteten med utfylte eksempler.":::

1. Velg **Lagre**.    
    Legg til flere data hvis det finnes andre kundeaktiviteter du vil inkludere.

1. Velg **Neste**.

### <a name="set-update-schedule"></a>Angi oppdateringstidsplan

1. I trinnet for **Tidsplan for dataoppdatering** velger du hyppigheten for å lære opp modellen på nytt basert på de nyeste dataene. Denne innstillingen er viktig for å oppdatere nøyaktigheten til prognoser når nye data hentes inn i målgruppeinnsikt. De fleste virksomheter kan gjenopplære én gang i måneden og få god nøyaktighet for prognosen.

1. Velg **Neste**.

### <a name="review-and-run-the-model-configuration"></a>Se gjennom og kjøre modellkonfigurasjonen

1. I trinnet **Se gjennom modelldetaljer** validerer du konfigurasjonen av prediksjonen. Du kan gå tilbake til en hvilken som helst del av forutsigelseskonfigurasjonen ved å velge **Rediger** under verdien som vises. Du kan også velge et konfigurasjonstrinn fra fremdriftsindikatoren.

1. Hvis alle verdier er riktig konfigurert, velger du **Lagre og kjør** for å begynne å kjøre modellen. På fanen **Mine prediksjoner** kan du se statusen for prediksjonsprosessen. Det kan ta flere timer før prosessen er fullført, avhengig av mengden data som brukes i forutsigelsen.

## <a name="review-prediction-status-and-results"></a>Se prediksjonstatus og -resultater

### <a name="review-prediction-status"></a>Se gjennom prediksjonsstatus

1.  Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.
2.  Velg prognosen du vil gå gjennom.

- **Navn på prediksjon**: Navnet på prediksjonen som ble angitt under opprettingen.
- **Prediksjontype**: Typen modell som brukes for prediksjonen
- **Utdataenhet**: Navn på enheten for å lagre utdataene fra prediksjonen. Gå til **Data** > **Enheter** for å finne enheten med dette navnet.
- **Forespeilet felt**: Dette feltet fylles bare ut for enkelte typer prediksjoner, og brukes ikke i predisjon av verdi for kundelevetid.
- **Status**: Statusen for prediksjonskjøringen.
    - **I kø**: Prediksjonen venter på at andre prosesser skal fullføres.
    - **Oppdaterer**: Prediksjonen kjører for å opprette resultater som flytes til utdataenheten.
    - **Mislyktes**: Prediksjonskjøringen mislyktes. [Se gjennom loggene](manage-predictions.md#troubleshoot-a-failed-prediction) for mer informasjon.
    - **Fullført**: Prediksjonen ble fullført. Velg **Vis** under de loddrette ellipsene for å se gjennom prediksjonsresultatene.
- **Redigert**: Datoen da konfigurasjonen av prediksjonen ble endret.
- **Sist oppdatert**: Datoen da prediksjonen oppdaterte resultater i utdataenheten.

### <a name="review-prediction-results"></a>Se gjennom prediksjonsresultater

1. Gå til **Intelligens** > **Prognoser**, og velg kategorien **Mine prognoser**.

1. Velg prediksjonen du vil se gjennom resultatene for.

Det er tre hoveddeler med data på resultatsiden.

- **Læringsmodellytelse**: A, B eller C er mulige vurderinger. Denne vurderingen angir ytelsen til prediksjonen og kan hjelpe deg med å ta avgjørelsen om å bruke resultatene som er lagret i utdataenheten. Velg **Finn ut mer om denne poengsummen** for å få bedre forståelse av de underliggende måleverdiene for modellytelse og hvordan den endelige ytelsesgraden for modellen ble utledet.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Bilde av boksen med informasjon om modellpoengsum med vurdering A.":::

  Ved hjelp av definisjonen av kunder med høy verdi under konfigurasjon av prediksjon, vurderer systemet hvordan modellen for kunstig intelligens gjorde det ved å forutsi kundene med høy verdi sammenlignet med en basismodell.    

  Vurderinger fastsettes basert på følgende regler:
  - **A** når modellen nøyaktig beregnet minst 5 % flere kunder med høy verdi sammenlignet med basismodellen.
  - **B** når modellen nøyaktig beregnet mellom 0–5 % flere kunder med høy verdi sammenlignet med basismodellen.
  - **C** når modellen nøyaktig beregnet færre kunder med høy verdi sammenlignet med basismodellen.

  Ruten **Modellrangering** viser flere detaljer om ytelsen til modellen for kunstig intelligens og basismodellen. Basismodellen bruker en ikke-AI-basert metode til å beregne verdie for kundelevetid, basert primært på historiske kjøp gjort av kunder.     
  Standardformelen som brukes til å beregne CLV etter basismodellen:    

  _**CLV for hver kunde** = Gjennomsnittlig månedlig kjøp gjort av kunden i det aktive kundevinduet * antall måneder i CLV-prediksjonsperioden * total oppbevaringsgrad for alle kunder*_

  Modellen for kunstig intelligens sammenlignes med basismodellen basert på to måleverdier for modellytelse.
  
  - **Prediksjonssuksess for kunder med høy verdi**

    Se forskjellen mellom å forutsi kunder med høy verdi ved hjelp av modellen for kunstig intelligens sammenlignet med basismodellen. Suksessrate på 84 % betyr for eksempel at av alle kunder med høy verdi i opplæringsdataene, kunne modellen for kunstig intelligens nøyaktig fange opp 84 %. Deretter sammenligner vi suksessgraden med suksessgraden for basismodellen for å rapportere den relative endringen. Denne verdien brukes til å tilordne en vurdering til modellen.

  - **Feilmåleverdier**
    
    Med en annen måleverdi kan du gå gjennom den totale ytelsen til modellen i form av feil når du skal forutsi fremtidige verdier. Vi bruker den totale RMSE-måleverdien (Root Mean Squared Error) til å vurdere denne feilen. RMSE er en standardmetode for å måle feilen for en modell ved prediksjon av kvantitative data. RMSE for modellen for kunstig intelligens sammenlignes med RMSE for basismodellen, og den relative forskjellen rapporteres.

  Modellen for kunstig intelligens prioriterer nøyaktig rangering av kunder i henhold til verdien de gir til virksomheten. Så bare suksessfrekvensen for å forutsi kunder med høy verdi brukes til å få den endelige modellgraden. RMSE-måleverdien er sensitiv for fordreininger. I scenarioer der du har en liten prosentandel av kundene med usedvanlig høye kjøpsverdier, kan det hende at den samlede RMSE-måleverdien ikke gir et fullstendig bilde av modellytelsen.   

- **Verdi for kunder etter persentil**: Ved hjelp av definisjonen av kunder med høy verdi grupperes kunder i lav verdi og høy verdi basert på CLV-prediksjonen, og de vises i et diagram. Når du holder markøren over stolpene i histogrammet, kan du se antall kunder i hver gruppe og den gjennomsnittlige CLV-en for gruppen. Disse dataene kan være til hjelp hvis du vil [opprette kundesegmenter](segments.md) basert på deres CLV-prediksjoner.

- **Mest innflytelsesrike faktorer**: Ulike faktorer vurderes når du oppretter CLV-prediksjon basert på inndataene som gis til modellen for kunstig intelligens. Hver av faktorene har sin viktighet beregnet for de aggregerte prognoser som opprettes av en modell. Du kan bruke disse faktorene til å validere forutsigelsesresultatene. Disse faktorene gir også mer innsikt i de mest innflytelsesrike faktorene som bidro til å forutsi CLV for alle kundene.

## <a name="manage-predictions"></a>Administrere prediksjoner

Det går an å optimalisere, feilsøke, oppdatere eller slette prognoser. Se gjennom en brukbarhetsrapport for inndata for å finne ut hvordan du gjør en prediksjon raskere og mer pålitelig. Hvis du vil ha mer informasjon, kan du se [Administrere prediksjoner](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
