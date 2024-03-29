---
title: Toegang tot werkstromen beheren
seo-title: Managing Access to Workflows
description: Leer hoe u de toegang tot Workflows beheert.
seo-description: Learn how to manage access to Workflows.
uuid: 58f79b89-fe56-4565-a869-8179c1ac68de
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 5150867a-02a9-45c9-b2fd-e536b60ffa8c
exl-id: 9c588691-0649-4d59-ab97-ebadfcd1252c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---

# Toegang tot werkstromen beheren{#managing-access-to-workflows}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Vorm ACLs volgens gebruikersrekeningen om het beginnen van, en het deelnemen aan, werkschema&#39;s toe te staan (of onbruikbaar te maken).

## Vereiste gebruikersmachtigingen voor workflows {#required-user-permissions-for-workflows}

Acties betreffende workflows kunnen worden uitgevoerd als:

* u werkt met de `admin` account
* de account is toegewezen aan de standaardgroep `workflow-users`:

   * deze groep beschikt over alle rechten die uw gebruikers nodig hebben om workflowhandelingen uit te voeren.
   * als de account in deze groep staat, heeft deze alleen toegang tot werkstromen die het heeft gestart.

* de account is toegewezen aan de standaardgroep `workflow-administrators`:

   * deze groep heeft alle rechten die nodig zijn voor uw geprivilegieerde gebruikers om workflows te controleren en beheren.
   * als de account zich in deze groep bevindt, heeft deze toegang tot alle workflows.

>[!NOTE]
>
>Dit zijn de minimumvereisten. Uw account moet ook de toegewezen deelnemer of een lid van de toegewezen groep zijn om specifieke stappen te kunnen uitvoeren.

## Toegang tot werkstromen configureren {#configuring-access-to-workflows}

De modellen van het werkschema erven een standaard toegangsbeheerlijst (ACL) voor het controleren hoe de gebruikers met werkschema&#39;s kunnen in wisselwerking staan. Om gebruikerstoegang voor een werkschema aan te passen, wijzig de Lijst van het Toegangsbeheer (ACL) in de bewaarplaats voor de omslag die de knoop van het werkschemamodel bevat:

* [Pas ACL voor het specifieke werkschemamodel op /var/workflow/modellen toe](/help/sites-administering/workflows-managing.md#apply-an-acl-for-the-specific-workflow-model-to-var-workflow-models)
* [Creeer een subfolder in /var/workflow/modellen en pas ACL op dat toe](/help/sites-administering/workflows-managing.md#create-a-subfolder-in-var-workflow-models-and-apply-the-acl-to-that)

>[!NOTE]
>
>Voor informatie over het gebruiken van CRXDE Lite om ACLs te vormen, zie [Toegangsbeheer](/help/sites-administering/user-group-ac-admin.md#access-right-management).

### Pas ACL voor het specifieke werkschemamodel op /var/workflow/modellen toe {#apply-an-acl-for-the-specific-workflow-model-to-var-workflow-models}

Als het workflowmodel is opgeslagen binnen `/var/workflow/models` dan kunt u specifieke ACL, relevant voor slechts dat werkschema, op de omslag toewijzen:

1. Open CRXDE Lite in uw webbrowser (bijvoorbeeld [http://localhost:4502/crx/de](http://localhost:4502/crx/de)).
1. Selecteer in de nodestructuur het knooppunt voor de map workflowmodellen:

   `/var/workflow/models`

1. Klik op de knop **Toegangsbeheer** tab.
1. In de **Beleid voor lokaal toegangsbeheer** (**Toegangsbeheerlijst**). **Item toevoegen**.
1. In de **Nieuw bericht toevoegen** voegt een nieuw ACE met de volgende eigenschappen toe:

   * **Opdrachtgever**: `content-authors`
   * **Type**: `Deny`
   * **Bevoegdheden**: `jcr:read`
   * **rep:glob**: verwijzing naar de specifieke workflow

   ![wf-108](assets/wf-108.png)

   De **Toegangsbeheerlijst** tabel bevat nu de beperking voor `content-authors` op de `prototype-wfm-01` workflowmodel.

   ![wf-109](assets/wf-109.png)

1. Klikken **Alles opslaan**.

   De `prototype-wfm-01` de workflow is niet meer beschikbaar voor leden van de `content-authors` groep.

### Creeer een subfolder in /var/workflow/modellen en pas ACL op dat toe {#create-a-subfolder-in-var-workflow-models-and-apply-the-acl-to-that}

Uw [ontwikkelingsteam kan de workflows in een submap maken](/help/sites-developing/workflows-models.md#creating-a-new-workflow) van

`/var/workflow/models`

Vergelijkbaar met de DAM-workflows die zijn opgeslagen onder

`/var/workflow/models/dam/`

U kunt ACL aan de omslag zelf dan toevoegen.

1. Open CRXDE Lite in uw webbrowser (bijvoorbeeld [http://localhost:4502/crx/de](http://localhost:4502/crx/de)).
1. Selecteer in de knooppuntstructuur het knooppunt voor de afzonderlijke map in de map met workflowmodellen. bijvoorbeeld:

   `/var/workflow/models/prototypes`

1. Klik op de knop **Toegangsbeheer** tab.
1. In de **Toepasselijk toegangsbeheerbeleid** tabel, klik op het plusteken naar **Toevoegen** een vermelding.
1. In de **Beleid voor lokaal toegangsbeheer** (**Toegangsbeheerlijst**). **Item toevoegen**.
1. In de **Nieuw bericht toevoegen** voegt een nieuw ACE met de volgende eigenschappen toe:

   * **Opdrachtgever**: `content-authors`
   * **Type**: `Deny`
   * **Bevoegdheden**: `jcr:read`

   >[!NOTE]
   >
   >Zoals met [Pas ACL voor het specifieke werkschemamodel op /var/workflow/modellen toe](/help/sites-administering/workflows-managing.md#apply-an-acl-for-the-specific-workflow-model-to-var-workflow-models) U kunt rep:glob opnemen om toegang tot een specifieke werkstroom te beperken.

   ![wf-110](assets/wf-110.png)

   De **Toegangsbeheerlijst** tabel bevat nu de beperking voor `content-authors` op de `prototypes` map.

   ![wf-111](assets/wf-111.png)

1. Klikken **Alles opslaan**.

   De modellen in de `prototypes` de map is niet meer beschikbaar voor leden van de `content-authors` groep.
