---
title: AEM Forms JEE Patch Installer
description: 'null'
uuid: e709871b-c04c-43bb-a7d0-45e89fbd3d44
content-type: reference
discoiquuid: 83bace08-1d4f-4192-a634-c7c4879963d8
translation-type: tm+mt
source-git-commit: 610e9a54adad3abdfecb8b2c4da67d677f75175e
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---


# AEM Forms JEE Patch Installer {#aem-forms-jee-patch-installer}

>[!NOTE]
>
>[Neem contact op met de ondersteuningsafdeling](https://www.adobe.com/account/sign-in.supportportal.html) voor meer informatie of om de patch te verkrijgen.

## Het installatieprogramma van de patch {#about-the-patch-installer}

Het AEM 6.4 Forms JEE-patchinstallatieprogramma bevat alle opgeloste problemen voor alle componenten van AEM 6.4 Forms JEE die beschikbaar zijn tot de release van deze patch. Zie de nieuwste [Cumulative Fix Pack Release-notities](cfp-release-notes.md) voor een volledige lijst met opgeloste problemen.

## Vereisten voor de installatie van de patch {#prerequisites-to-installing-the-patch}

* AEM 6.4 Forms

## De patch installeren en configureren {#installing-and-configuring-the-patch}

1. Maak een back-up van de &lt;*AEM_forms_root*>/implementatiemap. Dit is vereist als u besluit de snelle oplossing te verwijderen.
1. Stop uw toepassingsserver.
1. Pak het archiefbestand van het patch-installatieprogramma uit op de vaste schijf.
1. In de map met de naam volgens het besturingssysteem dat u gebruikt:

   * **Windows** Navigeer naar de juiste map op de installatiemedia of de installatiemap op de vaste schijf waarnaar u het installatieprogramma hebt gekopieerd en dubbelklik op de knop 
`aemforms64_cfp_install.exe` bestand.

      * (Windows 32-bits) `Windows\Disk1\InstData\VM`
      * (Windows 64-bits) `Windows_64Bit`\ `Disk1\InstData\VM`
   * **Linux, Solaris, AIX** Navigeer aan de aangewezen folder, en van een bevelherinnering, type 
`./aem64_cfp_install.bin`.

      * (Linux) `Linux/Disk1/InstData/NoVM`
      * (Solaris) `Solaris/Disk1/InstData/NoVM`
      * (AIX)

         ```
         AIX/Disk1/InstData/VM
         ```
   Hiermee wordt een installatiewizard gestart die u door de installatie begeleidt.

1. Klik in het deelvenster Introductie op **[!UICONTROL Next]**.
1. Controleer in het scherm Install Folder (Installatiemap kiezen) of de standaardlocatie correct is voor uw bestaande installatie of klik **[!UICONTROL Browse]** om de alternatieve map te selecteren waarin AEM formulieren zijn geïnstalleerd en klik op **[!UICONTROL Next]**.

1. Lees de informatie over het overzicht van reparaties in Snel repareren en klik op **[!UICONTROL Next]**.
1. Lees de informatie over het Pre-Installation Summary en klik op **[!UICONTROL Install]**.
1. Wanneer de installatie is voltooid, klikt u op **[!UICONTROL Next]** om de snelle reparatie-updates toe te passen op de geïnstalleerde bestanden.
1. [Alleen] Windows voert een van de volgende stappen uit:

   * Schakel de optie Configuratiebeheer starten uit voordat u op Gereed klikt. Voer later Configuration Manager uit met behulp van het `ConfigurationManager.bat` bestand in `[aem-forms root]\configurationManager\bin`. Door de naam van `ConfigurationManager.bat` axis.jar handmatig bij te werken in .lax-bestanden, voorkomt u
   * Schakel de optie Configuratiebeheer starten uit voordat u op Gereed klikt. Alvorens configuratiemanager in werking te stellen die **ConfigurationManager.exe** of **ConfigurationManager_IPv6.exe** gebruikt, navigeer aan *&lt;AEMForms_Install_Dir>\configurationManager\bin* folder en werk **axis.jar** aan **as-1.4.1.1.jar** in de volgende dossiers bij:

      * ConfigurationManager.lax
      * ConfigurationManager_IPv6.lax

1. (Alleen op Unix gebaseerd) Het selectievakje Configuratiebeheer starten is standaard ingeschakeld. Klik **[!UICONTROL Done]** om de Manager van de Configuratie in werking te stellen.

   Als u Configuratiebeheer later wilt uitvoeren, schakelt u de optie Configuratiebeheer starten uit voordat u op Gereed klikt. U kunt de Manager van de Configuratie later beginnen gebruikend het aangewezen manuscript in de `[AEM_forms_root]/configurationManager/bin` folder.

1. Afhankelijk van uw toepassingsserver kiest u een van de volgende documenten en volgt u de instructies in de sectie *Formulieren* configureren en implementeren.

   * [AEM voor JBoss installeren en implementeren](http://www.adobe.com/go/learn_aemforms_installJBoss_64)
   * [AEM voor WebSphere installeren en implementeren](http://www.adobe.com/go/learn_aemforms_installWebSphere_64)
   * [AEM voor WebLogic installeren en implementeren](http://www.adobe.com/go/learn_aemforms_installWebLogic_64)

1. (Alleen JBoss) Nadat u de patch hebt geïnstalleerd en de server hebt geconfigureerd, verwijdert u tmp- en werkmappen van de JBoss-toepassingsserver.

## Configuratie na implementatie {#post-deployment-configurations}

### SAML-configuraties {#saml-configurations}

Als u de authentificatie van SAML en het onder ogen zien van kwesties met grote meta-gegevens IDP had gevormd, doe het volgende na het installeren van het flard:

1. Stel de volgende systeemeigenschap in op uw toepassingsserver:\
   `um.saml.enable.large.xml=true`

1. Start de server opnieuw.
1. Verwijder bestaande SAML-auteproviders en voeg deze opnieuw toe voor bestaande domeinen zoals beschreven in SAML-instellingen.

## Betrokken modules {#impacted-modules}

* Document Services
* Documentbeveiliging
* Foundation JEE
* PDFG-service

[Contact opnemen met ondersteuning](https://www.adobe.com/account/sign-in.supportportal.html)
