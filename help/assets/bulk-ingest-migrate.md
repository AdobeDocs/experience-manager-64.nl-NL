---
title: Feature Pack 18912 installeren voor migratie van grote hoeveelheden bedrijfsmiddelen
seo-title: Feature Pack 18912 installeren voor migratie van grote hoeveelheden bedrijfsmiddelen
description: Met Feature Pack 18912 kunt u middelen in bulk opnemen via FTP of elementen migreren van Dynamic Media Classic naar Dynamic Media in AEM. Dit optionele functiepakket is beschikbaar bij de ondersteuning van Adobe.
seo-description: Met Feature Pack 18912 kunt u middelen in bulk opnemen via FTP of elementen migreren van Dynamic Media Classic naar Dynamic Media in AEM. Dit optionele functiepakket is beschikbaar bij de ondersteuning van Adobe.
uuid: 316d77e3-3d61-4cf0-8955-726ee54e268c
contentOwner: rbrough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 6198e613-a867-49a8-b9a5-a05e7889821c
translation-type: tm+mt
source-git-commit: b1603091bb05493c9cfffa6067f414f73774edb2
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---


# Functiepakket 18912 voor migratie van grote hoeveelheden bedrijfsmiddelen installeren {#installing-feature-pack}

De installatie van functiepak 18912 is _optioneel_.

Het pak van de eigenschap 18912 laat u of bulkingest activa direct in Dynamic Media - wijze Scene 7 op AEM door middel van FTP, of migrate activa van Dynamic Media Klassiek in Dynamic Media - wijze Scene7 op AEM. Het functiepakket is beschikbaar bij [Adobe Professional Services](https://www.adobe.com/experience-cloud/consulting-services.html).

>[!NOTE]
>
>Hoewel het voor u mogelijk is om het eigenschappak te gebruiken om activa op zich te bulken van Dynamic Media Klassiek aan Dynamic Media - wijze Scene 7 in AEM of bulkmigreren activa gebruikend de eigenschap van FTP in Dynamic Media Classic, adviseert Adobe deze methode *niet* wegens de ingewikkeldheid in kwestie.
>
>Migratiefunctiepakketten, zoals deze, worden daarom *alleen* ondersteund als onderdeel van een migratieproject via [Adobe Professional Services](https://www.adobe.com/experience-cloud/consulting-services.html).

Voordat u dit functiepakket kunt installeren, moet u eerst een servicegebruiker maken en die informatie aan Adobe doorgeven.

Zie ook het [Vormen Dynamic Media - wijze](https://helpx.adobe.com/experience-manager/6-4/assets/using/config-dms7.html)Scene7.

**Om functiepak 18912 voor de migratie** van bulkmiddelen te installeren,

1. Navigeer in uw AEM-instantie naar **[!UICONTROL Tools > Security > Users > Create User]**. Aan deze servicegebruiker moeten lees- en schrijfmachtigingen zijn toegewezen `/content/dam`.
1. Voer in de velden **[!UICONTROL ID]** en **[!UICONTROL Password]** velden een gebruikersnaam en wachtwoord in. bijvoorbeeld `FTP User`. Deze naam wordt in de tijdlijn weergegeven als de gebruiker die het element heeft gemaakt. Wanneer een element wordt geüpload vanaf FTP, wordt een element beschouwd als gemaakt wanneer het naar de FTP-server wordt geüpload en naar AEM wordt geduwd.
1. Neem contact op met de [Adobe Enterprise Support for Experience Manager](https://helpx.adobe.com/nl/contact/enterprise-support.ec.html) om toegang te vragen tot het functiepakket 18912 voor downloaden. U hebt mogelijk de volgende informatie nodig wanneer u contact opneemt met de ondersteuningsafdeling:

   * IP van de server adres voor uw instantie van de Auteur, met inbegrip van het havenaantal (door gebrek, is het havenaantal 4502).
   * Gebruikersnaam en wachtwoord voor AEM-service uit de vorige stap.

1. Adobe Enterprise Support for AEM biedt u de FTP-referenties en toegang tot functiepak 18912.

1. Wanneer u functiepakket 18912 ontvangt, installeert u dit.

   Zie [hoe te met pakketten](/help/sites-administering/package-manager.md) voor meer informatie over het gebruiken van de Distributie van de Software en pakketten in AEM werken.
