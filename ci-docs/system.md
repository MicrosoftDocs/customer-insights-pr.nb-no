---
title: Systemkonfigurasjon i Customer Insights
description: Lær om systeminnstillinger i Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 3aa4c6529d705698e612adad86587e3c3a4db35b
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653628"
---
# <a name="system-configuration"></a>Systemkonfigurasjon

Hvis du vil ha tilgang til systemkonfigurasjoner, går du til **Administrator** > **System** for å vise en liste over systemoppgaver og -prosesser.

**System**-siden inneholder følgende faner:
- [Status](#status-tab)
- [Tidsplan](#schedule-tab)
- [API-bruk](#api-usage-tab)
- [Om](#about-tab)
- [Generelt](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Innstillinger-faner på systemsiden.":::

## <a name="status-tab"></a>Kategorien Status

I **Kategorien Status** kan du spore fremdriften for oppgaver, datainntak, dataeksporter og flere andre viktige produktprosesser. Se gjennom informasjonen i denne kategorien for å sikre at de aktive oppgavene og prosessene er fullstendige.

Denne fanen inneholder tabeller med status og behandlingsinformasjon for ulike prosesser. Hver tabell sporer **navnet** på oppgaven og den tilsvarende enheten, **statusen** for den nyeste kjøringen og når den **sist ble oppdatert**. Du kan vise detaljene for de siste kjøringene ved å velge oppgave- eller prosessnavnet. 

Velg statusen ved siden av oppgaven eller prosessen i **Status**-kolonnen for å åpne **Fremdriftsdetaljer**-ruten.

   :::image type="content" source="media/system-progress-details.png" alt-text="Detaljruten for systemfremdrift":::

### <a name="status-definitions"></a>Statusdefinisjoner

Systemet bruker følgende statuser for oppgaver og prosesser:

|Status  |Definisjon  |
|---------|---------|
|Kansellert |Behandlingen ble avbrutt av brukeren før den ble fullført.   |
|Mislyktes   |Det oppstod en feil i datainnhentingen.         |
|Feil  |Behandling har mislyktes.  |
|Ikke startet   |Datakilden har ingen data som er tatt inn ennå, eller den er fremdeles i utkastmodus.         |
|Behandles  |Oppgave eller prosess pågår.  |
|Oppdaterer    |Datainntak pågår. Du kan avbryte denne operasjonen ved å velge **Stopp oppdatering** i kolonnen **Handlinger**. Hvis du stopper oppdateringen av en datakilde, blir den tilbakestilt til siste oppdateringstilstand.       |
|Hoppet over  |Hoppet over oppgave eller prosess. Én eller flere av de prosessene nedstrøms som denne oppgaven avhenger av, mislykkes eller blir hoppet over.|
|Vellykket  |Oppgave eller prosess er fullført. For datakilder, angir at dataene er inntakte hvis et tidspunkt er nevnt i kolonnen **Oppdatert**.|
|I kø | Behandlingen blir lagt i kø og starter når alle oppstrømsoppgaver og -prosesser er fullført. Hvis du vil ha mer informasjon, kan du se [Forretningsprosesser](#refresh-processes).|

### <a name="refresh-processes"></a>Oppdateringsprosesser

Oppdatering for oppgaver og prosesser kjøres i henhold til den [konfigurerte tidsplanen](#schedule-tab). 

|Behandle  |Beskrivelse  |
|---------|---------|
|Aktivitet  |Kjører manuelt (oppdatering én gang). Avhenger av sammenslåingsprosessen. Innsikt avhenger av behandlingen.|
|Analysekobling |Kjører manuelt (oppdatering én gang). Avhenger av segmenter.  |
|Analyseforberedelse |Kjører manuelt (oppdatering én gang). Avhenger av segmenter.  |
|Dataforberedelse   |Må ha en enhet for å kunne kjøre på. Datakildeenheter er avhengig av inntak. Supplerte enheter avhenger av suppleringer. Kundeenheten avhenger av sammenslåing.  |
|Datakilder   |Er ikke avhengig av andre prosesser. Samsvar avhenger av at denne prosessen er fullført.  |
|Suppleringer   |Kjører manuelt (oppdatering én gang). Avhenger av sammenslåingsprosessen. |
|Eksportmål |Kjører manuelt (oppdatering én gang). Avhenger av segmenter.  |
|Innsikt |Kjører manuelt (oppdatering én gang). Avhenger av segmenter.  |
|Intelligens   |Avhenger av fletting.   |
|Treff |Avhenger av behandlingen av datakildene som brukes i samsvarsdefinisjonen.      |
|Mål  |Kjører manuelt (oppdatering én gang). Avhenger av sammenslåingsprosessen.  |
|Flett   |Avhenger av at samsvarsprosessen er fullført. Segmenter, mål, supplering, søk, aktiviteter, prediksjoner og klargjøring av data avhenger av at denne prosessen er fullført.   |
|Profiler   |Kjører manuelt (oppdatering én gang). Avhenger av sammenslåingsprosessen. |
|Søk   |Kjører manuelt (oppdatering én gang). Avhenger av sammenslåingsprosessen. |
|Segmenter  |Kjører manuelt (oppdatering én gang). Avhenger av sammenslåingsprosessen. Innsikt avhenger av behandlingen.|
|System   |Avhenger av at samsvarsprosessen er fullført. Segmenter, mål, supplering, søk, aktiviteter, prediksjoner og klargjøring av data avhenger av at denne prosessen er fullført.   |
|User  |Kjører manuelt (oppdatering én gang). Avhengig av enheter.  |

Velg statusen for en prosess for å vise fremdriftsdetaljene for hele jobben den var i. Oppdateringsprosessene ovenfor kan hjelpe deg med å forstå hva du kan gjøre for å løse en oppgave eller prosess som er **Hoppet over** eller **Lagt i kø**.

## <a name="schedule-tab"></a>Kategorien Tidsplan

Bruk kategorien **Plan** til å planlegge automatisk oppdatering av alle [datakildene som er hentet inn](data-sources.md). Automatisk oppdatering bidrar til å sikre at oppdateringer fra datakildene gjenspeiles i de enhetlige kundeprofilene.

> [!NOTE]
> Datakilder som administreres av deg, oppdateres etter egne tidsplaner. Hvis du vil planlegge oppdatering av datakilder som administreres av deg, konfigurerer du oppdateringsinnstillinger for bestemte datakilde fra **Datakilder**-siden.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Oppdateringsinnstillinger for Power Platform-dataflyt.":::

1. Gå til **Administrator** > **System**, og velg fanen **Planlegg**.

2. Standardtilstanden for den planlagte oppdateringen er **Av**. Hvis du vil aktivere planlagte oppdateringer, endrer du vekslingsknappen øverst på skjermen til **På**.

3. Velg mellom **Ukentlig** (standard) og **Daglig** for oppdateringer. Hvis du planlegger ukentlige oppdateringer, velger du én eller flere dager du vil kjøre oppdateringen på.

4. Angi **Tidssone**, og bruk deretter rullegardinlisten **Tidspunkt** til å angi tiden for oppdatering. Velg **Angi** når du er ferdig. Hvis du vil planlegge flere repetisjoner på én enkelt dag, velger du **Legg til et annet tidspunkt**.

5. Velg **Lagre** for å ta i bruk endringene.

## <a name="about-tab"></a>Om kategori

Kategorien **Om** inneholder organisasjonens **visningsnavn**, den aktive **miljø-ID-en**, **området** og **økt-ID-en**. Hvis du har mer enn ett arbeidsmiljø, må du gi hvert av dem et enkelt identifiserbart visningsnavn.

## <a name="general-tab"></a>Generelt, kategori

Du kan endre språk- og land-/områdeformatet i fanen **Generelt**.

Customer Insights [støtter mange språk](/dynamics365/get-started/availability). Appen bruker språkpreferansen din til å vise elementer som menyen, etiketttekst og systemmeldinger på språket du foretrekker.

Importerte data og informasjon du har angitt manuelt, blir ikke oversatt.

### <a name="update-the-settings"></a>Oppdater innstillingene

Hvis du vil endre foretrukket språk, velger du et **Språk** fra rullegardinlisten.

Hvis du vil endre foretrukket formatering for datoer, klokkeslett og tall, bruker du rullegardinlisten **Lands-/områdeformat**. Det vises en formateringsforhåndsvisning under dette feltet. Systemet vil automatisk foreslå et valg når du velger et nytt språk.

Velg **Lagre** for å bekrefte valgene.

## <a name="api-usage-tab"></a>Kategorien API-bruk

Finn detaljer om API-bruk i sanntid, og se hvilke hendelser som har skjedd i en gitt tidsramme. Du velger tidsramme i rullegardinlisten **Velg en tidsramme**. 

**API-bruken** inneholder tre deler: 
- **API-kall** – et diagram som visualiserer det samlede antallet kall til API-en i den valgte tidsramme.

- **Dataoverføring** – et diagram som viser datamengden som ble overført via API-en i den valgte tidsramme.

-  **Operasjoner** – en tabell med rader for hver tilgjengelige API-operasjon og detaljer om bruken av operasjonene. Du kan velge et operasjonsnavn for å gå til [API-referansen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operasjoner som bruker [inntak av data i sanntid](real-time-data-ingestion.md), inneholder en knapp med et kikkertsymbol for å vise API-bruk i sanntid. Velg knappen for å åpne en siderute som inneholder bruksdetaljer for API-bruk i sanntid i det gjeldende miljøet.   
   Bruk **Grupper etter**-boksen i ruten for **API-bruk i sanntid** til å velge hvordan du best kan presentere samhandlinger i sanntid. Du kan gruppere dataene etter API-metode, enhetskvalifisertnavn (hentet enhet), opprettet av (kilde for hendelsen), resultat (vellykket eller mislykket) eller feilkoder. Dataene er tilgjengelige som et historikkdiagram og som en tabell.


[!INCLUDE [footer-include](includes/footer-banner.md)]
