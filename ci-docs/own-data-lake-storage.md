---
title: Bruk din egen Azure Data Lake Storage Gen2-konto
author: mukeshpo
description: Finn ut mer kravene for å bruke din egen Azure Data Lake Storage-konto til å lagre Customer Insights-data.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304393"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Bruk din egen Azure Data Lake Storage Gen2-konto

Dynamics 365 Customer Insights gir deg muligheten til å lagre alle dataene i [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). Ved å lagre data til Data Lake Storage godtar du at data overføres til og lagres på riktig geografisk sted for Azure Storage-kontoen. Hvis du vil ha mer informasjon om disse endringene, kan du se [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Administratorer i Customer Insights kan [opprette miljøer](create-environment.md) og [angi alternativet for datalagring](create-environment.md#step-2-configure-data-storage) i prosessen.

## <a name="prerequisites"></a>Forutsetning

- Azure Data Lake Storage-kontoer må være i samme Azure-område som du valgte da du opprettet Customer Insights-miljøet. For å finne ut området for miljøet går du til **Administrator** > **System** > **Om** i Customer Insights.
- Data Lake Storage-kontoen må være Gen2. Azure Data Lake Gen1-lagringskontoer støttes ikke.
- Azure Data Lake Storage-kontoen må ha [hierarkisk navneområde aktivert](/azure/storage/blobs/data-lake-storage-namespace).
- Det må finnes en beholder med navnet `customerinsights` på lagringskontoen. Opprett den før du bruker din egen Data Lake Storage i Customer Insights.
- Administrator som konfigurere Customer Insights-miljøet, må ha rollen Storage Blob Data-bidragsyter eller Storage Blob Data-eier på lagringskontoen eller beholderen `customerinsights`. Hvis du vil ha mer informasjon om tildeling av tillatelser i en lagringskonto, kan du se [Opprett en lagringskonto](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Koble Customer Insights til lagringskontoen

Når du oppretter et nytt miljø, må du sørge for at Data Lake Storage-kontoen finnes, og at alle forhåndskrav er oppfylt.

1. Angi **Lagre utdata** til **Azure Data Lake Storage Gen2** i trinnet **Datalagring** under oppretting av miljøet.
1. Velg hvordan du vil **koble til lagringsplassen**. Du kan velge mellom et ressursbasert alternativ og et abonnementsbasert godkjenningsalternativ. Hvis du vil ha mer informasjon, kan du se [Koble til en Azure Data Lake Storage-konto ved å bruke en Azure-tjenestekontohaver](connect-service-principal.md).
   - Velg **abonnementet**, **ressursgruppen** og **lagringskontoen** som inneholder beholderen `customerinsights`, for **Azure-abonnementet**.
   - For **Kontonøkkel** angir du **kontonavnet** og **kontonøkkelen** for Data Lake Storage-kontoen. Bruk av denne godkjenningsmetoden antyder at du er informert hvis organisasjonen roterer nøklene. Du må [oppdatere miljøkonfigurasjonen](manage-environments.md#edit-an-existing-environment) med den nye nøkkelen når den roteres.
1. Velg om du vil bruke Azure Private Link til å koble til lagringskontoen og [opprette tilkoblingen til Private Link](security-overview.md#set-up-an-azure-private-link).

Når systemprosesser som datainntak er fullført, oppretter systemet tilsvarende mapper i lagringskontoen. Datafiler og model.json-filer opprettes og legges til i mapper basert på prosessnavnet.

Hvis du oppretter flere miljøer med Customer Insights og velger å lagre utdataenhetene fra disse miljøene i lagringskontoen, oppretter Customer Insights separate mapper for hvert miljø med `ci_environmentID` i beholderen.
