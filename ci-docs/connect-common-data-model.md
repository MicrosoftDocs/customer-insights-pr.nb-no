---
title: Koble Common Data Model-til en Azure Data Lake-konto
description: Arbeid med Common Data Model-data ved hjelp av Azure Data Lake Storage.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2ab7ec77252be33f1203959c2a596ddec20425f2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011581"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Koble til data i Azure Data Lake Storage

Innta data i Dynamics 365 Customer Insights ved å bruke av Azure Data Lake Storage Gen2-kontoen. Datainntak kan være full eller trinnvis.

## <a name="prerequisites"></a>Forutsetning

- Datainntak støtter bare Azure Data Lake Storage *Gen2*-kontoer. Du kan ikke bruke Data Lake Storage Gen1-kontoer til å ta inn data.

- Azure Data Lake Storage-kontoen må ha [hierarkisk navneområde aktivert](/azure/storage/blobs/data-lake-storage-namespace). Dataene må lagres i et hierarkisk mappeformat som definerer rotmappen og har undermapper for hver enhet. Undermappene kan ha fullstendige data eller trinnvise datamapper.

- Når du skal godkjenne med en Azure-tjenestekontohaver, må den være konfigurert i leieren. Hvis du vil ha mer informasjon, kan du se [Koble til en Azure Data Lake Storage Gen2-med en en Azure-tjenestekontohaver](connect-service-principal.md).

- Azure Data Lake Storage du vil koble til og ta inn data fra, må være i samme Azure-område som Dynamics 365 Customer Insights-miljøet. Tilkoblinger til en Common Data Model-mappe fra en Data Lake-forekomst i et annet Azure-område støttes ikke. For å finne ut Azure-området for miljøet går du til **Administrator** > **System** > **Om** i Customer Insights.

- Data som er lagret i onlinetjenester, kan lagres på en annen plassering enn der data behandles eller lagres i Dynamics 365 Customer Insights. Ved å importere eller koble til data som er lagret i en onlinetjeneste, godtar du at dataene kan overføres til og lagres med Dynamics 365 Customer Insights. [Finn ut mer om Microsofts klareringssenter](https://www.microsoft.com/trust-center).

- Customer Insights-tjenestekontohaveren må være i en av følgende roller for å få tilgang til lagringskontoen. Hvis du vil ha mer informasjon, kan du se [Gi tillatelser til tjenestekontohaveren for å få tilgang til lagringskontoen](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Storage Blob-dataleser
  - Storage Blob-dataeier
  - Storage Blob-databidragsyter

- Data i Data Lake Storage skal følge Common Data Model-standarden for lagring av dataene og ha Common Data Model-manifestet for å representere skjemaet for datafilene (*.csv eller *.parquet). Manifestet må oppgi detaljene for enhetene, for eksempel enhetskolonner og datatyper, og datafilplasseringen og filtypen. Hvis du vil ha mer informasjon, kan du se [Common Data Model-manifestet](/common-data-model/sdk/manifest). Hvis manifestet ikke finnes, kan administratorbrukere med tilgang for Storage Blob-dataeier eller Storage Blob-databidragsyter angi skjemaet ved inntak av dataene.

## <a name="connect-to-azure-data-lake-storage"></a>Koble til Azure Data Lake Storage

1. Gå til **Data** > **Datakilder**.

1. Velg **Legg til datakilde**.

1. Velg **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialogboks for å angi tilkoblingsdetaljer for Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Angi et **Navn** for datakilden og en valgfri **beskrivelse**. Navnet identifiserer unikt datakilden og henvises til i nedstrømsprosesser og kan ikke endres.

1. Velg et av følgende alternativer for **Koble til lagringen ved hjelp av**. Hvis du vil ha mer informasjon, kan du se [Koble Customer Insights til en Azure Data Lake Storage Gen2-konto med en en Azure-tjenestekontohaver](connect-service-principal.md).

   - **Azure-ressurs**: Angi **ressurs-ID-en**. Hvis du eventuelt vil legge inn data fra en lagringskonto via en Azure Private Link, velger du **Aktiver privat kobling**. Hvis du vil ha mer informasjon, kan du se [Private koblinger](security-overview.md#private-links-tab).
   - **Azure-abonnement**: Velg **abonnementet** og deretter **ressursgruppen** og **lagringskontoen**. Hvis du eventuelt vil legge inn data fra en lagringskonto via en Azure Private Link, velger du **Aktiver privat kobling**. Hvis du vil ha mer informasjon, kan du se [Private koblinger](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Du må ha en av følgende roller i beholderen eller lagringskontoen for å opprette datakilden:
   >
   >  - Storage Blob Data-leser er tilstrekkelig for å lese fra en lagringskonto og registrere dataene i Customer Insights. 
   >  - Storage Blob Data-bidragsyter eller Eier er nødvendig hvis du vil redigere manifestfilene direkte i Customer Insights.  
  
1. Velg navnet på **beholderen** som inneholder dataene og skjemaet (model.json- eller manifest.json-fil) du vil importere data fra, og velg **Neste**.
   > [!NOTE]
   > En model.json- eller manifest.json-fil som er tilknyttet en annen datakilde i miljøet, vises ikke i listen. Den samme model.json- eller manifest.json-filen kan imidlertid brukes for datakilder i flere miljøer.

1. Hvis du vil opprette et nytt skjema, går du til [Opprett en ny skjemafil](#create-a-new-schema-file).

1. Hvis du vil bruke et eksisterende skjema, navigerer du til mappen som inneholder filen model.json eller manifest.cdm.json. Du kan søke i en katalog for å finne filen.

1. Velg JSON-filen og deretter **Neste**. Det vises en liste over tilgjengelige enheter.

   :::image type="content" source="media/review-entities.png" alt-text="Dialogboksen for en liste over entiteter som kan velges":::

1. Velg enhetene du vil ta med.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogboksen Obligatorisk for primærnøkkel":::

   > [!TIP]
   > Hvis du vil redigere enhetene i et JSON-redigeringsgrensesnitt, velger du **Vis mer** > **Rediger skjemafil**. Foreta endringene og velg **Lagre**.

1. For valgte enheter som krever trinnvis inntak, vises **Obligatorisk** vises under **Trinnvis oppdatering**. For hver av disse enhetene kan du se [Konfigurer en trinnvis oppdatering for Azure Data Lake-datakilder](incremental-refresh-data-sources.md).

1. For valgte enheter der en primærnøkkel ikke er definert, vises **Obligatorisk** under **Primærnøkkel**. For hver av disse enhetene:
   1. Velg **Obligatorisk**. Panelet **Rediger enhet** vises.
   1. Velg **primærnøkkelen**. Primærnøkkelen er et attributt som er unikt for enheten. For at et attributt skal være en gyldig primærnøkkel, bør den ikke inneholde duplikate verdier, manglende verdier eller nullverdier. Datatypeattributtene streng, heltall og GUID støttes som primærnøkler.
   1. Du kan eventuelt endre partisjonsmønsteret.
   1. Velg **Lukk** for å lagre lukke panelet.

1. Velg antall **attributter** for hver inkluderte enhet. Siden **Administrer attributter** vises.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogboks for valg av dataprofilering.":::

   1. Opprett nye attributter, rediger eller slett eksisterende attributter Du kan endre navnet, dataformatet eller legge til en semantisk type.
   1. Hvis du vil aktivere analyse og andre funksjoner, velger du **Dataprofilering** for hele enheten eller for bestemte attributter. Som standard er ingen enheter aktivert for dataprofilering.
   1. Velg **Ferdig**.

1. Velg **Lagre**. Siden **Datakilder** åpnes med den nye datakilde i statusen **Oppdaterer**.

### <a name="create-a-new-schema-file"></a>Opprett en ny skjemafil

1. Velg **Ny skjemafil**.

1. Skriv inn et navn for filen, og velg deretter **Lagre**.

1. Velg **Ny enhet**. Panelet **Ny enhet** vises.

1. Skriv inn enhetsnavnet, og velg **plasseringen for datafilene**.
   - **Flere .csv- eller .parquet-filer**: Bla til rotmappen, velg mønstertypen og angi uttrykket.
   - **Enkle .csv- eller .parquet-filer**: Bla til .csv- eller .parquet-filen, og velg den.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialogboks for oppretting av en ny enhet med plasseringen av datafilene uthevet.":::

1. Velg **Lagre**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialogboks for å definere eller generere attributter automatisk.":::

1. Velg **Definer attributtene** for manuelt å legge til attributtene, eller velg **Generer dem automatisk**. Hvis du vil definere attributtene, angir du et navn, velger dataformatet og den valgfrie semantiske typen. For automatisk genererte attributter:

   1. Når attributtene er generert automatisk, velger du **Se gjennom attributter**. Siden **Administrer attributter** vises.

   1. Kontroller at dataformatet er riktig for hvert attributt.

   1. Hvis du vil aktivere analyse og andre funksjoner, velger du **Dataprofilering** for hele enheten eller for bestemte attributter. Som standard er ingen enheter aktivert for dataprofilering.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogboks for valg av dataprofilering.":::

   1. Velg **Ferdig**. Siden **Velg enheter** vises.

1. Fortsett for å legge til enheter og attributter hvis aktuelt.

1. Når alle enhetene er lagt til, velger du **Inkluder** for å inkludere enhetene i datakildeinntaket.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogboksen Obligatorisk for primærnøkkel":::

1. For valgte enheter som krever trinnvis inntak, vises **Obligatorisk** vises under **Trinnvis oppdatering**. For hver av disse enhetene kan du se [Konfigurer en trinnvis oppdatering for Azure Data Lake-datakilder](incremental-refresh-data-sources.md).

1. For valgte enheter der en primærnøkkel ikke er definert, vises **Obligatorisk** under **Primærnøkkel**. For hver av disse enhetene:
   1. Velg **Obligatorisk**. Panelet **Rediger enhet** vises.
   1. Velg **primærnøkkelen**. Primærnøkkelen er et attributt som er unikt for enheten. For at et attributt skal være en gyldig primærnøkkel, bør den ikke inneholde duplikate verdier, manglende verdier eller nullverdier. Datatypeattributtene streng, heltall og GUID støttes som primærnøkler.
   1. Du kan eventuelt endre partisjonsmønsteret.
   1. Velg **Lukk** for å lagre lukke panelet.

1. Velg **Lagre**. Siden **Datakilder** åpnes med den nye datakilde i statusen **Oppdaterer**.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Rediger en Azure Data Lake Storage-datakilde

Du kan oppdatere alternativet *Koble til lagringskonto ved hjelp av*. Hvis du vil ha mer informasjon, kan du se [Koble Customer Insights til en Azure Data Lake Storage Gen2-konto med en en Azure-tjenestekontohaver](connect-service-principal.md). Hvis du vil koble til en annen beholder fra lagringskontoen, eller endre navnet på forretningsforbindelsen, må du [opprette en ny datakilde-tilkobling](#connect-to-azure-data-lake-storage).

1. Gå til **Data** > **Datakilder**.

1. Ved siden av datakilde du vil oppdatere, velger du **Rediger**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialogboks for å redigere Azure Data Lake-datakilde.":::

1. Endre eventuelt følgende informasjon:

   - **Bekrivelse**
   - **Koble til lagringen ved hjelp av** og tilkoblingsinformasjon. Du kan ikke endre informasjon om en **beholder** når du oppdaterer tilkoblingen.
      > [!NOTE]
      > En av følgende roller må være tildelt til lagringskontoen eller beholderen:
        > - Storage Blob-dataleser
        > - Storage Blob-dataeier
        > - Storage Blob-databidragsyter

   - **Aktiver privat kobling** hvis du eventuelt vil legge inn data fra en lagringskonto via en Azure Private Link. Hvis du vil ha mer informasjon, kan du se [Private koblinger](security-overview.md#private-links-tab).

1. Velg **Neste**.
1. Endre eventuelt følgende:
   - Naviger til en annen model.json- eller manifest.json-fil med et annet sett enheter fra beholderen.
   - Hvis du vil legge til flere enheter i inntaket, velger du **Ny enhet**.
   - Hvis du vil fjerne alle allerede valgte enheter hvis det ikke finnes avhengigheter, velger du enheten og **Slett**.
      > [!IMPORTANT]
      > Hvis det finnes avhengigheter i den eksisterende model.json- eller manifest.json-filen og enhetene, vises en feilmelding og du kan ikke velge en annen model.json- eller manifest.json-fil. Fjern avhengighetene før du endrer model.json- eller manifest.json-filen, eller opprett en ny datakilde med model.json- eller manifest.json-filen som du vil bruke for å unngå å fjerne avhengighetene.
   - Hvis du vil endre datafilplasseringen eller primærnøkkelen, velger du **Rediger**.
   - Hvis du vil endre de trinnvise inntaksdataene, kan du se [Konfigurer en trinnvis oppdatering for Azure Data Lake-datakilder](incremental-refresh-data-sources.md)

1. Velg **Attributter** for å legge til eller endre attributter, eller for å aktivere dataprofilering. Deretter velger du **Ferdig**.

1. Klikk på **Lagre** for å ta i bruk endringene, og gå tilbake til siden **Datakilder**.
