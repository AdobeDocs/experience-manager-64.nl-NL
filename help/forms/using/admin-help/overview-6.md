---
title: Overzicht van het configureren van SSL
seo-title: Overview of configuring SSL
description: Leer over hoe te om veiligheid van mededeling te verbeteren door SSL te vormen.
seo-description: Learn about how to enhance security of communication by configuring SSL.
uuid: 3e99d2bf-137b-45ba-8384-309624094623
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_ssl
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 8e107abb-861f-4063-b600-c87e34639019
exl-id: 5dc68401-f6bc-42cb-84db-1db805b045c5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---

# Overzicht van het configureren van SSL {#overview-of-configuring-ssl}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt SSL-referenties (Secure Sockets Layer) maken en SSL op de toepassingsserver configureren om de communicatie met uw toepassingsserver te verbeteren.

Als beveiligingsproduct vereist Rights Management de configuratie van SSL. Wanneer het vormen van SSL certificaten, zorg ervoor dat u slechts sleutels RSA gebruikt. SSL-certificaten met DSA-sleutels worden niet ondersteund.

De verstrekte informatie is van toepassing op kant-en-klare, automatische en handmatige installaties. Het biedt een voorbeeld van een methode voor het vormen van SSL aan. U kunt andere methodes ook gebruiken die voor uw netwerk of organisatie geschikter zijn.

>[!NOTE]
>
>Het wordt aanbevolen dat u de installatie, configuratie en implementatie van uw AEM formuliermodules voltooit en ervoor zorgt dat de producten correct worden uitgevoerd voordat u SSL op de toepassingsserver configureert.

>[!NOTE]
>
>Wanneer u SSL-beveiligingscertificaten en -referenties maakt, gebruikt u dezelfde gebruikersaccountrechten als waarmee u de toepassingsserver hebt uitgevoerd. Als de toepassingsserver wordt uitgevoerd met andere gebruikersrechten, wordt het formulier mogelijk niet correct weergegeven voor PDFForm-uitvoeringen wanneer ContentRootURI naar https wijst.

Als u een LDAP-server met SSL-functionaliteit hebt, configureert u Gebruikersbeheer voor samenwerking met deze server. (Zie [Gebruikersbeheer configureren voor een LDAP-server die geschikt is voor SSL](/help/forms/using/admin-help/configure-user-management-ssl-enabled.md#configure-user-management-for-an-ssl-enabled-ldap-server).)
