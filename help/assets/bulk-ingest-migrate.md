---
title: Feature Pack 18912 installeren voor migratie van grote hoeveelheden bedrijfsmiddelen
seo-title: Feature Pack 18912 installeren voor migratie van grote hoeveelheden bedrijfsmiddelen
description: Met Feature Pack 18912 kunt u middelen bulksgewijs innemen via FTP of middelen migreren van Dynamic Media Classic naar Dynamic Media in AEM. Dit optionele functiepakket is verkrijgbaar bij Adobe-ondersteuning.
seo-description: Met Feature Pack 18912 kunt u middelen bulksgewijs innemen via FTP of middelen migreren van Dynamic Media Classic naar Dynamic Media in AEM. Dit optionele functiepakket is verkrijgbaar bij Adobe-ondersteuning.
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


# Installeren van functiepak 18912 voor het migreren van grote bedrijfsmiddelen {#installing-feature-pack}

De installatie van functiepak 18912 is _optioneel_.

Met Feature Pack 18912 kunt u opgenomen elementen rechtstreeks in Dynamic Media - Scene 7-modus AEM via FTP, of elementen migreren van Dynamic Media Classic naar Dynamic Media - Scene7-modus bij AEM. Het functiepakket is beschikbaar bij [Adobe Professional Services](https://www.adobe.com/experience-cloud/consulting-services.html).

>[!NOTE]
>
>Hoewel het voor u mogelijk is om het eigenschappak te gebruiken om activa op zich van de Klassiek van Dynamic Media aan Dynamic Media - wijze Scene 7 in AEM of bulkmiddel te migreren migrate activa gebruikend de eigenschap van FTP in Dynamic Media Classic, *niet* adviseert Adobe deze methode wegens de ingewikkeldheid in kwestie.
>
>Als dusdanig, worden de pakketten van de migratieeigenschap, zoals dit, *slechts* gesteund als deel van een migratieproject door [Adobe Professional Services](https://www.adobe.com/experience-cloud/consulting-services.html).

Voordat u dit functiepakket kunt installeren, moet u eerst een servicegebruiker maken en die informatie aan Adobe verstrekken.

Zie ook [Dynamic Media configureren - Scene7-modus](https://helpx.adobe.com/experience-manager/6-4/assets/using/config-dms7.html).

**Om functiepak 18912 voor de migratie** van bulkmiddelen te installeren,

1. Navigeer in uw AEM naar **[!UICONTROL Tools > Security > Users > Create User]**. Deze servicegebruiker moet lees- en schrijfmachtigingen hebben voor `/content/dam`.
1. Voer in de velden **[!UICONTROL ID]** en **[!UICONTROL Password]** een gebruikersnaam en wachtwoord in. bijvoorbeeld `FTP User`. Deze naam wordt in de tijdlijn weergegeven als de gebruiker die het element heeft gemaakt. Wanneer een element wordt geüpload vanaf FTP, wordt een element beschouwd als gemaakt wanneer het naar de FTP-server wordt geüpload en naar AEM wordt geduwd.
1. Neem contact op met [Adobe Enterprise Support for Experience Manager](https://helpx.adobe.com/nl/contact/enterprise-support.ec.html) om toegang te vragen tot functiepak 18912 voor downloaden. U hebt mogelijk de volgende informatie nodig wanneer u contact opneemt met de ondersteuningsafdeling:

   * IP van de server adres voor uw instantie van de Auteur, met inbegrip van het havenaantal (door gebrek, is het havenaantal 4502).
   * AEM de gebruikersbenaming en het wachtwoord van de dienstgebruiker van de vorige stap.

1. Adobe Enterprise Support for AEM biedt u de FTP-referenties en toegang tot functiepak 18912.

1. Wanneer u functiepakket 18912 ontvangt, installeert u dit.

   Zie [Werken met pakketten](/help/sites-administering/package-manager.md) voor meer informatie bij het gebruiken van de Distributie van de Software en pakketten in AEM.
