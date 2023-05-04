---
title: AEM Forms JEE Patch Installer
description: AEM Forms JEE Patch Installer
uuid: e709871b-c04c-43bb-a7d0-45e89fbd3d44
content-type: reference
discoiquuid: 83bace08-1d4f-4192-a634-c7c4879963d8
exl-id: ce5300ce-03f4-4e7b-bc5b-01a9968ebe06
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 0%

---

# AEM Forms JEE Patch Installer {#aem-forms-jee-patch-installer}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>[Contact opnemen met ondersteuning](https://www.adobe.com/account/sign-in.supportportal.html) voor meer informatie of om de pleister te verkrijgen.

## Het installatieprogramma van de patch {#about-the-patch-installer}

Het AEM 6.4 Forms JEE-patchinstallatieprogramma bevat alle opgeloste problemen voor alle componenten van AEM 6.4 Forms JEE die beschikbaar zijn tot de release van deze patch. Zie de nieuwste  [Opmerkingen bij de release Cumulative Fix Pack](cfp-release-notes.md) voor een volledige lijst van opgeloste problemen.

## Vereisten voor de installatie van de patch {#prerequisites-to-installing-the-patch}

* AEM 6.4 Forms

## De patch installeren en configureren {#installing-and-configuring-the-patch}

1. Maak een back-up van de &lt;*AEM_forms_root*>/implementatiemap. Dit is vereist als u besluit de snelle oplossing te verwijderen.
1. Stop uw toepassingsserver.
1. Pak het archiefbestand van het patch-installatieprogramma uit op de vaste schijf.
1. In de map met de naam volgens het besturingssysteem dat u gebruikt:

   * **Windows**
Navigeer naar de juiste directory op de installatiemedia of de installatiemap op de vaste schijf waarnaar u het installatieprogramma hebt gekopieerd en dubbelklik op de knop 
`aemforms64_cfp_install.exe` bestand.

      * (Windows 32-bits) `Windows\Disk1\InstData\VM`
      * (Windows 64-bits) `Windows_64Bit`\ `Disk1\InstData\VM`
   * **Linux, Solaris, AIX**
Navigeer aan de aangewezen folder, en van een bevelherinnering, type 
`./aem64_cfp_install.bin`.

      * (Linux) `Linux/Disk1/InstData/NoVM`
      * (Solaris) `Solaris/Disk1/InstData/NoVM`
      * (AIX)

         ```
         AIX/Disk1/InstData/VM
         ```
   Hiermee wordt een installatiewizard gestart die u door de installatie begeleidt.

1. Klik in het deelvenster Inleiding op **[!UICONTROL Next]**.
1. Controleer in het scherm Installatiemap kiezen of de standaardlocatie die wordt weergegeven correct is voor uw bestaande installatie of klik op **[!UICONTROL Browse]** om de alternatieve map te selecteren waarin AEM formulieren zijn geïnstalleerd en klik op **[!UICONTROL Next]**.

1. Lees de informatie over het overzicht van reparaties in Snel repareren en klik op **[!UICONTROL Next]**.
1. Lees de informatie van het Pre-installatieoverzicht en klik **[!UICONTROL Install]**.
1. Wanneer de installatie is voltooid, klikt u op **[!UICONTROL Next]**om de snelle moeilijke fixupdates op uw geïnstalleerde dossiers toe te passen.
1. [Alleen Windows] Voer een van de volgende stappen uit:

   * Schakel de optie Configuratiebeheer starten uit voordat u op Gereed klikt. De Manager van de Configuratie van de looppas later door `ConfigurationManager.bat` bestand in `[aem-forms root]\configurationManager\bin`. Gebruiken `ConfigurationManager.bat` helpt u te vermijden manueel het bijwerken van naam van axis.jar in .lax dossiers
   * Schakel de optie Configuratiebeheer starten uit voordat u op Gereed klikt. Voordat u configuratiebeheer uitvoert **ConfigurationManager.exe** of **ConfigurationManager_IPv6.exe**, navigeer naar *&lt;aemforms_install_dir>\configurationManager\bin* map en update **axis.jar** tot **as-1.4.1.1.jar** in de volgende bestanden:

      * ConfigurationManager.lax
      * ConfigurationManager_IPv6.lax

1. (Alleen Unix-gebaseerd) Het selectievakje Configuratiebeheer starten is standaard ingeschakeld. Klikken **[!UICONTROL Done]** om de Manager van de Configuratie in werking te stellen.

   Als u Configuratiebeheer later wilt uitvoeren, schakelt u de optie Configuratiebeheer starten uit voordat u op Gereed klikt. U kunt de Manager van de Configuratie later beginnen gebruikend het aangewezen manuscript in `[AEM_forms_root]/configurationManager/bin` directory.

1. Afhankelijk van uw toepassingsserver kiest u een van de volgende documenten en volgt u de instructies in het dialoogvenster *Formulieren configureren en implementeren AEM* sectie.

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
