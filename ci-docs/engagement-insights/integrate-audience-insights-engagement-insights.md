---
title: Opprett en kobling mellom målgruppeinnsikt og engasjementsinnsikt
description: Opprett en aktiv kobling mellom målgruppeinnsikt og engasjementsinnsikt for å muliggjøre toveis deling av data.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d93a49a29c29103e189a6d4a42294c18dc28abd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/27/2021
ms.locfileid: "7559030"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Opprett en kobling mellom målgruppeinnsikt og engasjementsinnsikt

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integrasjonen mellom engasjementsinnsikt og målgruppeinnsikt kobler miljøer fra begge funksjonene, og gjør det mulig å dele data toveis mellom dem.

Bruk enhetlige profiler og segmenter fra målgruppeinnsikt til å få flere analysealternativer i engasjementsinnsikt. Eksporter hendelser som har høy forretningsverdi fra engasjementsinnsikt. Bruk disse hendelsene til å legge til data i enhetlige profiler i målgruppeinnsikt.

## <a name="prerequisites"></a>Forutsetninger

- Målgruppeinnsiktsprofiler må lagres i en Azure Data Lake Storage-konto som du eier, eller i en [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)-administrert datasjø. 
- Målgruppeinnsiktmiljøet må også ha et tilknyttet Dataverse-miljø. Og hvis det miljøet også bruker Dataverse for datalagring, må du kontrollere at du merker av for alternativet **Aktiver datadeling** i målgruppeinnsikt. Hvis du vil ha mer informasjon, kan du se [Opprett og konfigurer et betalt miljø i målgruppeinnsikt](../audience-insights/get-started-paid.md).
- Du trenger administratortillatelser for både engasjementsinnsikts- og målgruppeinnsiktsmiljøene.
- Koblede miljøer må være i samme geografiske område.

> [!NOTE]
> - Hvis abonnementet for målgruppeinnsikt er en prøveversjon, som bruker en målgruppeinnsiktinternt administrert datasjø, kan du kontakte [pirequest@microsoft.com](mailto:pirequest@microsoft.com) for å få hjelp. 
> - Hvis målgruppeinnsiktmiljøet bruker din egen Azure Data Lake Storage til å lagre data, må du legge til en Azure-tjenestekontohaver for engasjementsinnsikt i lagringskontoen. Hvis du vil ha mer informasjon, kan du gå til [Koble til en Azure Data Lake Storage-konto med en Azure-tjenestekontohaver for målgruppeinnsikt](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Opprett en miljøkobling

Du kan opprette en miljøkobling ved å oppdatere innstillingene **Administrator** > **Miljø** i engasjementsinnsikt.

**Slik oppretter du en aktiv kobling mellom målgruppeinnsikt og engasjementsinnsikt**

1. Velg fanen **Koble miljø** på siden **Miljøadministrator**.

    :::image type="content" source="media/integrate1.png" alt-text="Konfigurer et miljø.":::

1. Velg **Konfigurer miljøer** øverst til venstre eller nederst på skjermen.

     :::image type="content" source="media/integrate2.png" alt-text="Velg et miljø for målgruppeinnsikt.":::

1. Velg et målgruppeinnsiktsmiljø, og velg deretter ***Neste** for å fullføre. Nå kan du velge valgfrie funksjoner for de koblede miljøene.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Aktiver attributter og segmenter for enhetlige profiler for målgruppeinnsikt

Når du har koblet miljøer, kan du velge valgfrie funksjoner for de koblede miljøene. Disse funksjonene aktiverer enhetlige profilattributter og segmenter fra målgruppeinnsikt for interaktiv analyse av kundedata.

> [!IMPORTANT]
> Hvis målgruppeinnsiktssegmenter skal vises i engasjementsinnsikt, må du først [kjøre sammenslåings- og nedstrømsprosesser](../audience-insights/merge-entities.md). Nedstrømsprosesser er viktige fordi de genererer en unik tabell som klargjør målgruppeinnsiktssegmenter som skal deles med engasjementsinnsikt. (Hvis en systemoppdatering planlegges, vil den automatisk inkludere nedstrømsprosesser.)

**Slik analyserer du nettdata i engasjementsinnsikt**

1. På **Miljøadministrator**-siden aktiverer du **Del data fra målgruppeinnsikt med engasjementsinnsikt**, og deretter velger du **Neste**.

    :::image type="content" source="media/integrate4.png" alt-text="Velg funksjoner.":::

1. Velg attributtene for de enhetlige profilene som blir dimensjonene i engasjementsinnsikt. (Ikke alle attributter er nyttige dimensjoner. Det er for eksempel ikke sannsynlig at du trenger **fornavn** eller **etternavn** som et attributt for analyse av hendelser på nettstedet.)

    :::image type="content" source="media/integrate5.png" alt-text="Kurater dimensjoner.":::

   >[!NOTE]
   > Alle målgruppeinnsiktsprofilattributter som representerer identifikatorer (for eksempel **ID** og **alternativ ID**), filtreres ut av de tilgjengelige attributtene og blir dimensjoner i engasjementsinnsikt.

1. Når du er ferdig med å velge attributter, velger du **Neste**.
1. Legg til brukere som kan vise målgruppeinnsiktsprofildimensjoner og segmenter i engasjementsinnsikt.

    :::image type="content" source="media/integrate6.png" alt-text="Administrer tilgang til kundedata.":::

   > [!IMPORTANT]
   > Hvis du ikke eksplisitt legger til brukere i dette trinnet, blir dataene skjult for brukere i engasjementsinnsikt.
   > Hvis målgruppeinnsiktssegmenter skal vises i engasjementsinnsikt, må du først [kjøre sammenslåings- og nedstrømsprosesser](../audience-insights/merge-entities.md). Nedstrømsprosesser er viktige fordi de genererer en unik tabell som klargjør målgruppeinnsiktssegmenter som skal deles med engasjementsinnsikt. (Hvis en systemoppdatering planlegges, vil den automatisk inkludere nedstrømsprosesser.)

1. Se gjennom det du har valgt, og velg deretter **Fullfør**.

    :::image type="content" source="media/integrate7.png" alt-text="Se gjennom innstillingene for kundedata.":::

## <a name="export-refined-events-to-audience-insights"></a>Eksporter begrensede hendelser til målgruppeinnsikt

Når du har opprettet en kobling mellom miljøer, kan du eksportere begrensede hendelser fra engasjementsinnsikt til målgruppeinnsikt og legge dem inn som en ny datakilde. 

Hvis du vil ha mer informasjon, kan du gå til [Integrer nettdata fra engasjementsinnsikt med målgruppeinnsikt](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
