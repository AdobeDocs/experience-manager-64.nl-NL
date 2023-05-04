---
title: Een Correspondentiebeheeroplossing configureren
seo-title: Configuring a Correspondence Management solution
description: Leer hoe u een instantie-URL van de auteur definieert voor het herstellen van de versie van de auteurinstantie en hoe u de URL van de instantie Publiceren definieert voor het openbare Instance Activation Manager.
seo-description: Learn how to define an author instance URL for the author instance version restore and define the Publish instance URL for public instance activation manager.
uuid: 76b25004-fe47-44d7-9bed-7c0fd963306b
topic-tags: correspondence-management
content-type: reference
products: SG_EXPERIENCEMANAGER/6.3/FORMS
discoiquuid: 186ca75c-638b-4057-826e-cd5d56aa0397
feature: Correspondence Management
exl-id: a062957d-a526-4c4b-bbc5-0cda8ab007a3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Een Correspondentiebeheeroplossing configureren {#configuring-a-correspondence-management-solution}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## URL van auteurinstantie voor VersionRestoreManagerImpl bepalen {#defining-author-instance-url-for-versionrestoremanagerimpl}

Gebruik de volgende stappen om een instantie-URL van de auteur te definiëren voor het terugzetten van de auteurversie:

1. Ga naar *https://:&lt;publishhost>:&lt;publishport>/lc/system/console/configMgr*. Meld u aan met de gebruikersgegevens van de OSGi Management Console. De standaardreferenties zijn admin/admin.
1. Zoeken en klikken op de knop **[!UICONTROL Edit]** pictogram naast **[!UICONTROL com.adobe.livecycle.content.activate.impl.VersionRestoreManagerImpl.name]** instellen.
1. In de **[!UICONTROL VersionRestoreManager Author URL]** Geef de URL van de instantie Auteur van VersionRestoreManager op.

   **URL-tekenreeks**:

   `https://<hostname>:<port>:/libs/fd/fdm/content/crud/lc.content.remote.activate.VersionRestoreManager`

   >[!NOTE]
   >
   >Als er meerdere auteur-instanties (geclusterd) zijn met een taakverdeler, geeft u de URL op naar het taakverdelingsmechanisme in het dialoogvenster **[!UICONTROL VersionRestoreManager Author URL]** veld.

1. Klik op **[!UICONTROL Save]**.

## De URL van de instantie Publish definiëren voor ActivationManagerImpl (public instance activation manager) {#defining-the-publish-instance-url-for-activationmanagerimpl-public-instance-activation-manager}

Voer de volgende stappen uit om de URL van de instantie Publiceren te definiëren voor het beheer voor activering van openbare instanties:

1. Ga naar *https://:&lt;authorhost>:&lt;authorport>/lc/system/console/configMgr*. Meld u aan met de gebruikersgegevens van de OSGi Management Console. De standaardreferenties zijn admin/admin.
1. Zoeken en klikken op de knop **[!UICONTROL Edit]** pictogram naast **[!UICONTROL com.adobe.livecycle.content.activate.impl.ActivationManagerImpl.name]** instellen.
1. In de **[!UICONTROL ActivationManager Publish URL]** Geef de URL op voor toegang tot de instantie Publish ActivationManager. U kunt de volgende URL&#39;s opgeven.

   * **Load Balancer URL (aanbevolen)**: Geef een URL voor het taakverdelingsmechanisme op als u een webserver hebt die als taakverdelingsmechanisme fungeert vóór het publicatiefarm (meerdere niet-geclusterde publicatieinstanties).
   * **Instance-URL publiceren**: Geef een URL voor een publicatieexemplaar op als u één publicatieexemplaar hebt of als de webserver die de publicatiecapaciteit doorstuurt, niet toegankelijk is vanuit de auteursomgeving vanwege beperkingen. Als de opgegeven publicatie-instantie is ingedrukt, is er een fallback-mechanisme waarmee aan de auteurzijde moet worden omgegaan.
   * **URL-tekenreeks**:

      `https://<hostname>:<port>:/libs/fd/fdm/content/crud/lc.content.remote.activate.activationManager`

1. Klik op **[!UICONTROL Save]**.

Voor meer informatie over het vormen van het Beheer van de Correspondentie, zie [Eigenschappen van Correspondentenbeheer](https://helpx.adobe.com/aem-forms/6-2/cm-configuration-properties.html).
