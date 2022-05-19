---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755556"
---
Når dataene er innhentes, starter du datasamlingsprosessen for å opprette en enhetlig kundeprofil. Hvis du vil ha mer informasjon, kan du se [Dataforening](../data-unification.md).

### <a name="select-source-fields"></a>Velg kildefelter

1. Etter at du har hentet inn dataene, tilordner du kontakter fra eCommerce og lojalitetsdata til vanlige datatyper. Gå til **Data** > **Samle**.

1. Velg enhetene som representerer kundeprofilen – **eCommerceContacts** og **loyCustomers**.

   ![Samle ecommerce- og lojalitetsdatakildene.](../media/unify-ecommerce-loyalty.png)

1. Velg **ContactId** som primærnøkkelen for **eCommerceContacts** og **LoyaltyID** som primærnøkkelen for **loyCustomers**.

1. Velg **Neste**. Hopp over duplikatoppføringer, og velg **Neste**.

### <a name="match-conditions"></a>Samsvar betingelser

1. Velg **eCommerceContacts : eCommerce** som primærenhet, og inkluder alle oppføringer.

1. Velg **loyCustomers : LoyaltyScheme**, og inkluder alle oppføringer.

1. Legg til en regel:
   - Velg **FullName** for både eCommerceContacts og loyCustomers.
   - Velg **Type (telefon, navn, adresse ...)** for **Normaliser**.
   - Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.
   - Skriv inn **FullName, Email** for navnet.

1. Legg til en ny betingelse for e-postadresse:
   - Velg **Email** for både eCommerceContacts og loyCustomers.
   - La Normaliser være tomt.
   - Angi **Presisjonsnivå**: **Grunnleggende** og **Verdi**: **Høy**.

   ![Regel for å samle treff for navn og e-post.](../media/unify-match-rule.png)

1. Velg **Ferdig**.

1. Velg **Neste**.

### <a name="unify-fields"></a>Samle felter

1. Endre navnet på **ContactId** for **loyCustomers**-enhetentil **ContactIdLOYALTY** for å skille den fra de andre ID-ene som er inntatt.

1. Velg **Neste** for å se gjennom, og velg deretter **Opprett kundeprofiler**.
