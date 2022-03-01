---
title: Administrer informasjonskapsler og brukersamtykke for å lagre brukerdata
description: Forstå hvordan informasjonskapsler og brukersamtykke brukes til å identifisere besøkende på nettstedet.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036750"
---
# <a name="manage-cookies-and-user-consent"></a>Administrere informasjonskapsler og brukersamtykke

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funksjonen Dynamics 365 Customer Insights-engasjementsinnsikt bruker informasjonskapsler og lokal lagring (`localStorage`) til å identifisere besøkende på nettstedet.

Informasjonskapsler er små filer som lagrer biter av informasjon om en brukers samhandling med nettstedet. De lagres i nettlesere. Når brukere går til et nettsted som brukerne har lagret informasjonskapsler for, sender nettleseren informasjonen til serveren, som returnerer informasjon som er unik for brukeren. Dette er teknologien som gjør det mulig å for eksempel beholde valgte varer i en handlekurv på nettet selv om en bruker navigerer seg bort fra nettstedet.

## <a name="user-consent"></a>Brukersamtykke

[EUs personvernforordning (GDPR)](/dynamics365/get-started/gdpr/) er en EU-forskrift som dikterer hvordan organisasjoner skal håndtere brukernes personvern og sikkerhet. Informasjonskapsler lagrer eller samler ofte inn personlige opplysninger, for eksempel en elektronisk identifikator, som dekkes av GDPR. Hvis virksomheten din bruker eller selger til EU-dataemner, gjelder GDPR for deg. [Finn ut mer om hvordan Microsoft kan hjelpe deg med å overholde GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Hvis SDK-en for engasjementsinnsikt skal kunne lagre informasjonskapsler eller annen sensitiv informasjon, må du angi om brukerne har samtykket. Dette skjer ved initialisering av SDK.

Hvis du angir at det ikke er brukersamtykke, lagrer ikke SDK noen data og sender ikke hendelser som kan brukes til å spore brukeratferd. Tidligere lagrede data blir slettet fra nettleseren.

Hvis ingen brukersamtykkeverdi er angitt, forutsetter SDK-en at brukeren har samtykket. Dette betyr at hvis du (som vår kunde) ikke angir en verdi for brukersamtykke i SDK-en, samles det inn data. Hvis du imidlertid angir at verdien for brukersamtykke må være sann, samles ikke data inn hvis en bruker avslår eller ikke gir eksplisitt samtykke.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Datalagring for besøkende i engasjementsinnsiktfunksjonalitet

### <a name="cookies"></a>Kaker

- _msei
    - Lagrer den anonyme bruker-ID-en. Denne informasjonskapselen angis i kundedomenet og utløper om 365 dager.

### <a name="local-storage"></a>Lokal lagring

Engasjementsinnsiktsfunksjonalitet bruker også lokalt lager (`localStorage`) til å spore ikke-sensitive data. Disse dataene lagres i selve nettleseren uten at det sendes trafikk til eller fra serverne.

- *EISession.Id* 
    - Lagrer informasjon om den pågående brukerøkten, for eksempel økt-ID, når den startes, og når den utløper.
- *EISession.Previous*
    - Lagrer URL-adressen til den tidligere besøkte siden i gjeldende økt.
    
Nøkler i lokal lagring utløper ikke automatisk. De tilbakestilles i løpet av den neste økten av SDK-en.

## <a name="deleting-cookies"></a>Slette av informasjonskapsler

Kundene dine kan når som helst slette informasjonskapsler og nøkler for lokal lagring manuelt via innstillingene i nettleseren.


[!INCLUDE[footer-include](../includes/footer-banner.md)]