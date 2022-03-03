---
title: Vanlige spørsmål om prøveversjon – Dynamics 365 Customer Insights
description: Svar på vanlige spørsmål knyttet til konfigurasjon og administrasjon av Customer Insights-prøveversjon. Finn ut hvordan du løser plattform- og appspesifikke problemer.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 9badd8370358b9f5745ba6347e8db42e89c5f3d3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229507"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Vanlige spørsmål om prøveversjonen av Dynamics 365 Customer Insights

## <a name="sign-up"></a>Registrering

### <a name="what-are-the-system-requirements-for-the-trial"></a>Hva er systemkravene for prøveversjonen?

Denne appen er en skybasert tjeneste som ikke krever annen programvare enn en oppdatert nettleser, men noen restriksjoner gjelder. For å få best mulig prøveversjonsopplevelse bør du unngå å gå til prøveversjonsområdet i inkognitomodus og velge prøveplasseringen som er nærmest deg. [Finn ut mer om krav til nettprogram.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Hvordan registrerer jeg meg for prøveversjonen uten en Microsoft 365-leier?

Du kan angi en e-postadresse som ikke er for jobben, og så oppretter vi en konto og leier for deg.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Kan jeg registrere meg for flere Dynamics 365-apper, for eksempel Sales, Marketing og Customer Service?

Ja, det kan du. Hvis du vil vise alle tilgjengelige prøveversjoner, [kan du gå til siden for prøveversjonshuben](https://dynamics.microsoft.com/dynamics-365-free-trial). Du kan bruke den samme e-postkontoen til å registrere deg for ulike prøveversjoner. Du kan imidlertid ikke ha flere apper på det samme nettstedet for prøveversjon. Hver prøveversjon er på en egen organisasjon og nettadresse. Prøveversjonsdataene deles ikke på tvers av apper.

## <a name="trial-app"></a>Prøveversjonsapp

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Jeg har ikke mottatt e-posten med prøvedetaljene etter registreringen. Hva skal jeg gjøre?

Når du registrerer deg for prøveversjonen, mottar du en e-postmelding med detaljene for prøveversjonen. Hvis du ikke ser e-postmeldingen i innboksen, kan du se i søppelpostmappen. Du kan også følge denne fremgangsmåten for å få tilgang til appen:

1. Gå til nettstedet, og velg **Prøv gratis**.
1. Skriv inn e-post-ID-en du brukte for å registrere deg for prøveversjonen. Du blir omdirigert til prøveappen.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Hvordan legger jeg til flere brukere i en prøveversjon?

Du kan legge til brukere ved å gå til [administrasjonssenteret for Microsoft 365](https://admin.microsoft.com) ved å bruke administratorkontoen for prøveversjon. Følg [veiledningen for administrasjonssenteret](/microsoft-365/admin/add-users/add-users) for å legge til brukere opptil lisensgrensen for prøveversjonen. Hvis brukeren du legger til, allerede har en Microsoft 365-konto, tilordner du en aktuell sikkerhetsrolle til vedkommende i prøveorganisasjonen. Hvis du vil ha mer informasjon, kan du se [Tilordne en sikkerhetsrolle til en bruker](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Hvor mange brukere kan jeg legge til i prøvemiljøet?

Du kan legge til et ubegrenset antall brukere i prøveversjonsmiljøet.

### <a name="how-do-i-reset-the-trial-environment"></a>Hvordan tilbakestiller jeg prøveversjonsmiljøet?

Du kan ikke tilbakestille prøveversjonsmiljøet. Du kan imidlertid vente til prøveperioden er over og deretter registrere deg på nytt for en ny prøveperiode.

## <a name="trial-expiration-and-extension"></a>Utløp og forlengelse av prøveversjonen

### <a name="how-do-i-extend-the-trial"></a>Hvordan forlenger jeg prøveversjonen?

Du kan utvide prøveversjonen i appen direkte. Du kan utvide prøveversjonen én gang.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Kan jeg konvertere prøveversjonen til en betalt lisens?

Generelt anbefaler vi at du starter på nytt med dine egne data når du oppgraderer til den betalte versjonen av Customer Insights. 

Hvis du bare bruker målgruppeinnsikt, kan du eventuelt kopiere dataene fra et prøvemiljø hvis du kjøper Customer Insights. Du må være administrator for prøveversjonen av Customer Insights og den globale administratoren av Microsoft 365-leieren din eller Dynamics 365-administrator i organisasjonen for å overføre innstillingene fra et prøvemiljø til et betalt miljø. 

Etter at du har logget på den betalte forekomsten av Customer Insights for første gang, blir du bedt om å opprette et nytt miljø. I denne prosessen kan du velge å kopiere konfigurasjonen fra et eksisterende miljø og overføre de fleste innstillingene. Hvis du har tillatelsene nevnt ovenfor, vises prøveversjonsmiljøet i denne listen. Hvis du vil ha mer informasjon, kan du se [Kopier miljøkonfigurasjonen](audience-insights/manage-environments.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Hva er begrensningene og kvotene for prøveversjonen?

- Du kan ikke bruke din egen Azure Data Lake Storage-konto til å lagre utdata i en prøveversjon av målgruppeinnsikt. Du kan imidlertid innta data fra en Data Lake-lagringskonto.
- Du kan lagre opptil 3 GB data i Dataverse-miljøet som klargjøres automatisk når du starter en prøveversjon av Customer Insights.

## <a name="customer-insights-specific-questions"></a>Spørsmål om Customer Insights spesifikt

### <a name="how-do-i-start-using-the-trial"></a>Hvordan begynner jeg å bruke prøveversjonen?

Etter at du har registrert deg for prøveversjonen, vises hovedskjermen i appen. Hovedskjermen inneholder koblinger til brukerveiledninger og opplæring. Hvis du vil vite mer, kan du gå til koblingene i [Ytterligere ressurser](trial-signup.md#additional-resources) på registreringssiden for prøveversjonen.

### <a name="what-features-are-available-in-the-trial"></a>Hvilke funksjoner er tilgjengelige i prøveversjonen?

De fleste funksjonene i Customer Insights er tilgjengelige i prøveversjonen.

Følgende funksjoner er **ikke tilgjengelige**: 
- Du kan ikke opprette nye miljøer som bruker din egen Azure Data Lake Storage-konto.
- Du kan ikke slette prøveversjonsmiljøet. 

### <a name="how-long-does-the-trial-last"></a>Hvor lenge varer prøveversjonen?

Prøveversjonen av Customer Insights varer i 30 dager. Du kan utvide prøveversjonen én gang etter 23 dager når du logger på prøvemiljøet.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Hvordan fjerner jeg eksempeldata fra prøveversjonen?

Du kan ikke fjerne eksempeldata fra prøveversjonen.
