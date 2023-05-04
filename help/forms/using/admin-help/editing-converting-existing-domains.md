---
title: Bestaande domeinen bewerken en converteren
seo-title: Editing and converting existing domains
description: Leer hoe u de instellingen voor bestaande domeinen wijzigt via de pagina Domeinbeheer. Zet een bestaand ondernemingsdomein in een hybride domein om of vice versa.
seo-description: Learn how to change the settings for existing domains from the Domain Management page. Convert an existing enterprise domain to a hybrid domain or vice versa.
uuid: 4cc9547e-b4ec-4588-b1cf-18720f06149a
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/setting_up_and_managing_domains
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 44dec184-3ef7-4ba6-a87f-ad171d3cb188
exl-id: 07ca7715-f7b3-40e0-95bc-e05f0662ed08
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 0%

---

# Bestaande domeinen bewerken en converteren{#editing-and-converting-existing-domains}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt de montages voor bestaande domeinen van de pagina van het Beheer van het Domein veranderen. U kunt een bestaand ondernemingsdomein ook omzetten in een hybride domein.

## Een bestaand domein bewerken {#edit-an-existing-domain}

1. Klik in de beheerconsole op Instellingen > Gebruikersbeheer > Domeinbeheer.
1. Klik op de naam van het domein dat u wilt bewerken.
1. Als u de domeinnaam wilt wijzigen, wijzigt u de tekst in het vak Naam.
1. Om de authentificatieinformatie voor een onderneming of hybride domein te veranderen, klik de aangewezen authentificatienaam bij de bodem van de pagina. Wijzig desgewenst de instellingen op de pagina Verificatie bewerken. (Zie [Verificatieinstellingen](/help/forms/using/admin-help/configuring-authentication-providers.md#authentication-settings).)
1. Als u de mapinformatie voor een ondernemingsdomein wilt wijzigen, klikt u op de juiste mapnaam onder aan de pagina. Wijzig desgewenst de instellingen op de pagina Directory bewerken. (Zie [Mappen of aangepaste SPI&#39;s toevoegen](/help/forms/using/admin-help/configuring-directories.md#adding-directories-or-custom-spis).)
1. Klik op OK als u de wijzigingen hebt aangebracht.

## Een ondernemingsdomein omzetten in een hybride domein {#convert-an-enterprise-domain-to-a-hybrid-domain}

1. Klik in de beheerconsole op Instellingen > Gebruikersbeheer > Domeinbeheer.
1. Klik op de naam van het ondernemingsdomein dat u wilt converteren.
1. Klik op Omzetten in hybride domein.
1. Controleer de informatie die wordt weergegeven met betrekking tot gebruikers- en groepsgegevens en verificatie van gebruikers en klik op OK.
1. Bewerk de instellingen voor het hybride domein en klik op OK.

>[!NOTE]
>
>Als het ondernemingsdomein dat u omzet geen foldermontages bevat, worden om het even welke montages van de authentificatie LDAP verloren.

## Een hybride domein omzetten in een ondernemingsdomein {#convert-a-hybrid-domain-to-an-enterprise-domain}

1. Klik in de beheerconsole op Instellingen > Gebruikersbeheer > Domeinbeheer.
1. Klik op de naam van het hybride domein dat u wilt omzetten.
1. Klik op Omzetten in Enterprise-domein.
1. Controleer de informatie die wordt weergegeven met betrekking tot gebruikers- en groepsgegevens en verificatie van gebruikers en klik op OK.
1. Klik toevoegen Folder en vormen de vereiste folderinformatie. (Zie [Mappen of aangepaste SPI&#39;s toevoegen](/help/forms/using/admin-help/configuring-directories.md#adding-directories-or-custom-spis).)
