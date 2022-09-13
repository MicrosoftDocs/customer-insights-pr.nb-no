---
title: Vis systemkonfigurasjon
description: Lær om systeminnstillinger i Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396013"
---
# <a name="view-system-configuration"></a>Vis systemkonfigurasjon

Vis systeminformasjon, systemstatus og API-bruk.

## <a name="view-api-usage"></a>Vis API-bruk

Vis detaljer om API-bruk i sanntid, og se hvilke hendelser som har skjedd i en gitt tidsramme.

1. Gå til **Administrator** > **System**, og velg fanen **API-bruk**.

1. **Velg en tidsramme** du vil vise.

   Siden **API-bruken** inneholder tre deler:

   - **API-kall** – et diagram som visualiserer det samlede antallet kall til API-en i den valgte tidsramme.
   - **Dataoverføring** – et diagram som viser datamengden som ble overført via API-en i den valgte tidsramme.
   - **Operasjoner** – en tabell med rader for hver tilgjengelige API-operasjon og detaljer om bruken av operasjonene. Velg et operasjonsnavn for å gå til [API-referansen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

## <a name="view-system-information"></a>Vis systeminformasjon

Vis miljøet og visningsnavn, ID, område, type og økt-ID.

1. Gå til **Administrator** > **System**, og velg fanen **Om**.

1. Velg fanen **Generelt** for å vise språk og land/område.

### <a name="update-preferred-language-or-countryregion"></a>Oppdater foretrukket språk eller land/område

Customer Insights [støtter mange språk](/dynamics365/get-started/availability). Appen bruker språkpreferansen din til å vise elementer som menyen, etiketttekst og systemmeldinger på språket du foretrekker.

Importerte data og informasjon du har angitt manuelt, blir ikke oversatt.

1. Gå til **Administrator** > **System**, og velg fanen **Generelt**.

1. Hvis du vil endre foretrukket språk, velger du et **Språk** fra rullegardinlisten.

1. Hvis du vil endre foretrukket formatering for datoer, klokkeslett og tall, bruker du rullegardinlisten **Lands-/områdeformat**. En formateringsforhåndsvisning vises. Systemet foreslår automatisk et valg når du velger et nytt språk.

1. Velg **Lagre**.

## <a name="view-system-status"></a>Vis systemstatus

Spor fremdriften for oppgaver, datainntak, dataeksporter og flere andre viktige produktprosesser. Se gjennom informasjonen for å sikre at de aktive oppgavene og prosessene er fullstendige.

1. Gå til **Administrator** > **System**, og velg fanen **Status**.

   Status og behandlingsinformasjon for ulike prosesser vises. Vis **navnet** på oppgaven, **statusen** for den nyeste kjøringen og når den **sist ble oppdatert**.

1. For å vise detaljene for de siste kjøringene velger du oppgave- eller prosessnavnet.

1. Hvis du vil vise fremdriftsdetaljene for en oppgave, velger du statusen. **Fremdriftsdetaljer**-ruten vises.

   :::image type="content" source="media/system-progress-details.png" alt-text="Detaljruten for systemfremdrift":::

1. Hvis du vil vise fremdriftsdetaljer for alle oppgavene, velger du **Hele arbeidsflyten**.

### <a name="status-definitions"></a>Statusdefinisjoner

Systemet bruker følgende statuser for oppgaver og prosesser:

|Status  |Definisjon  |
|---------|---------|
|Kansellert |Oppgave eller prosess ble avbrutt av brukeren før den ble fullført.   |
|Mislyktes   |Det oppstod feil under oppgave eller prosess.         |
|Feil  |Oppgaven eller prosessen mislyktes.  |
|Ikke startet   |Datakilden har ingen data som er tatt inn ennå, eller oppgaven er fremdeles i utkastmodus.         |
|Behandles  |Oppgave eller prosess pågår.  |
|Oppdaterer    |Oppgave eller prosess pågår. Hvis du vil avbryte denne operasjonen, velger du **Oppdater** og **Avbryt jobben**. Hvis du stopper oppdateringen av en oppgave eller prosess, blir den tilbakestilt til siste oppdateringstilstand.       |
|Hoppet over  |Hoppet over oppgave eller prosess. Én eller flere av de prosessene nedstrøms som denne oppgaven avhenger av, mislykkes eller blir hoppet over.|
|Vellykket  |Oppgave eller prosess er fullført. For datakilder, angir at dataene er inntakte hvis et tidspunkt er nevnt i kolonnen **Oppdatert**.|
|I kø | Behandlingen blir lagt i kø og starter når alle oppstrømsoppgaver og -prosesser er fullført. Hvis du vil ha mer informasjon, kan du se [Forretningsprosesser](#refresh-processes).|

### <a name="refresh-processes"></a>Oppdateringsprosesser

Oppdatering for oppgaver og prosesser kjøres i henhold til den [konfigurerte tidsplanen](schedule-refresh.md).

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
