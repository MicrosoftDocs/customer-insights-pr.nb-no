---
title: Systemkonfigurasjon i målgruppeinnsikt
description: Lær om systeminnstillinger i funksjonen for målgruppeinnsikt i Dynamics 365 Customer Insights.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 32bb89b02947350c056c8ce8adbe37500d2099a1
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556090"
---
# <a name="system-configuration"></a>Systemkonfigurasjon

**System**-siden inneholder følgende faner:
- [Status](#status-tab)
- [Tidsplan](#schedule-tab)
- [API-bruk](#api-usage-tab)
- [Om](#about-tab)
- [Generelt](#general-tab)

> [!div class="mx-imgBorder"]
> ![Systemside.](media/system-tabs.png "Systemside")

## <a name="status-tab"></a>Kategorien Status

I fanen **Status** kan du spore fremdriften for datainntak, dataeksporter og flere andre viktige produktprosesser. Se gjennom informasjonen i denne kategorien for å sikre at aktive prosesser er fullført.

Denne fanen inneholder tabeller med status og behandlingsinformasjon for ulike prosesser. Hver tabell sporer **navnet** på oppgaven og den tilsvarende enheten, **statusen** for den nyeste kjøringen og når den **sist ble oppdatert**.

Du kan vise detaljene for de siste kjøringene av oppgaven ved å velge navnet på den.

### <a name="status-types"></a>Statustyper

Det finnes seks typer statuser for oppgaver. Følgende statustyper vises også på sidene *Samsvar*, *Slå sammen*, *Datakilder*, *Segmenter*, *Mål*, *Supplering*, *Aktiviteter* og *Prediksjoner*:

- **Behandling:** Oppgave pågår. Statusen kan endres til vellykket eller mislykket.
- **Vellykket:** Oppgaven er fullført.
- **Hoppet over:** Oppgaven ble hoppet over. Én eller flere av de prosessene nedstrøms som denne oppgaven avhenger av, mislykkes eller blir hoppet over.
- **Feil:** Behandlingen av oppgaven mislyktes.
- **Avbrutt:** Behandlingen ble avbrutt av brukeren før den var ferdig.
- **I kø:** Behandlingen blir lagt i kø og starter når alle oppstrømsoppgavene er fullført. Hvis du vil ha mer informasjon, kan du se [Oppdateringspolicyer](#refresh-policies).

### <a name="refresh-policies"></a>Oppdateringspolicyer

Denne listen viser oppdateringspolicyene for hver av hovedprosessene:

- **Datakilder:** Kjører i henhold til den [konfigurerte tidsplanen](#schedule-tab). Er ikke avhengig av andre prosesser. Samsvar avhenger av at denne prosessen er fullført.
- **Samsvar:** Kjører i henhold til den [konfigurerte tidsplanen](#schedule-tab). Avhenger av behandlingen av datakildene som brukes i samsvarsdefinisjonen. Slå sammen avhenger av at denne prosessen er fullført.
- **Slå sammen**: Kjører i henhold til den [konfigurerte tidsplanen](#schedule-tab). Avhenger av at samsvarsprosessen er fullført. Segmenter, mål, supplering, søk, aktiviteter, prediksjoner og klargjøring av data avhenger av at denne prosessen er fullført.
- **Segmenter**: Kjører manuelt (engangsoppdatering) og i henhold til den [konfigurerte tidsplanen](#schedule-tab). Avhenger av fletting. Innsikt avhenger av behandlingen.
- **Mål**: Kjører manuelt (engangsoppdatering) og i henhold til den [konfigurerte tidsplanen](#schedule-tab). Avhenger av fletting.
- **Aktiviteter**: Kjører manuelt (engangsoppdatering) og i henhold til den [konfigurerte tidsplanen](#schedule-tab). Avhenger av fletting.
- **Supplering**: Kjører manuelt (engangsoppdatering) og i henhold til den [konfigurerte tidsplanen](#schedule-tab). Avhenger av fletting.
- **Søk**: Kjører manuelt (engangsoppdatering) og i henhold til den [konfigurerte tidsplanen](#schedule-tab). Avhenger av fletting.
- **Dataforberedelse**: Kjører i henhold til den [konfigurerte tidsplanen](#schedule-tab). Avhenger av fletting.
- **Innsikt**: Kjører manuelt (engangsoppdatering) og i henhold til den [konfigurerte tidsplanen](#schedule-tab). Avhenger av segmenter.

Velg statusen for en oppgave for å vise detaljer om fremdriften for hele jobben den var i. Oppdateringspolicyene over kan hjelpe deg med å forstå hva du kan gjøre for å løse en oppgave av typen **Hoppet over** eller **I kø**.

## <a name="schedule-tab"></a>Kategorien Tidsplan

Bruk kategorien **Plan** til å planlegge automatisk oppdatering av alle [datakildene som er hentet inn](data-sources.md). Automatisk oppdatering bidrar til å sikre at oppdateringer fra datakildene gjenspeiles i de enhetlige kundeprofilene.

1. I Målgruppeinnsikt går du til **Administrasjon** > **System** og velger kategorien **Plan**.

2. Standardtilstanden for den planlagte oppdateringen er **Av**. Hvis du vil aktivere planlagte oppdateringer, endrer du vekslingsknappen øverst på skjermen til **På**.

3. Velg mellom **Ukentlig** (standard) og **Daglig** for oppdateringer. Hvis du planlegger ukentlige oppdateringer, velger du én eller flere dager du vil kjøre oppdateringen på.

4. Angi **Tidssone**, og bruk deretter rullegardinlisten **Tidspunkt** til å angi tiden for oppdatering. Velg **Angi** når du er ferdig. Hvis du vil planlegge flere repetisjoner på én enkelt dag, velger du **Legg til et annet tidspunkt**.

5. Velg **Lagre** for å ta i bruk endringene.

## <a name="about-tab"></a>Om kategori

Kategorien **Om** inneholder organisasjonens **visningsnavn**, den aktive **miljø-ID-en**, **området** og **økt-ID-en**. Hvis du har mer enn ett arbeidsmiljø, må du gi hvert av dem et enkelt identifiserbart visningsnavn.

## <a name="general-tab"></a>Generelt, kategori

Det finnes to alternativer i kategorien **Generelt**, **Språk** og **Lands-/områdeformat**.

Appen [støtter flere språk](supported-languages.md). Hvis du vil endre foretrukket språk, velger du et **Språk** fra rullegardinlisten.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]