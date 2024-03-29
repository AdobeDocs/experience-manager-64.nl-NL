---
title: Back-ups maken van de EMC Documentum-opslagplaats en deze herstellen
seo-title: Backing up and recovering the EMC Documentum repository
description: In dit document worden de taken beschreven die nodig zijn om back-ups te maken van de EMC Documentum-opslagplaats die is geconfigureerd voor uw AEM formulieromgeving.
seo-description: This document describes the tasks required to back up and recover the EMC Documentum repository configured for your AEM forms environment.
uuid: ab3b1fb1-25b3-4c95-801f-82d4b58f05ff
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/aem_forms_backup_and_recovery
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: f146202f-25f1-46a0-9943-c483f5f09f9f
exl-id: 89d7b2e1-1d88-4392-89d3-484a98f07121
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 0%

---

# Back-ups maken van de EMC Documentum-opslagplaats en deze herstellen {#backing-up-and-recovering-the-emc-documentum-repository}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

In deze sectie worden de taken beschreven die nodig zijn om back-ups te maken van de EMC Documentum-opslagplaats die is geconfigureerd voor uw AEM formulieromgeving.

>[!NOTE]
>
>In deze instructies wordt ervan uitgegaan dat AEM formulieren met Connectors voor ECM en EMC Documentum Content Server geïnstalleerd en geconfigureerd zijn zoals vereist.

Voor zowel het back-up- als het herstelproces zijn er twee hoofdtaken:

* Back-up maken van de AEM formulieromgeving (of deze herstellen).
* Back-up maken van (of herstellen van) de EMC Documentum Content Server.

>[!NOTE]
>
>Maak een back-up van uw AEM formuliergegevens voordat u een back-up maakt van het EMC Documentum systeem en herstel vervolgens het EMC Documentum systeem voordat u de AEM formulieromgeving herstelt.

## Softwarevereisten {#software-requirements}

Om de noodzakelijke back-uptaken uit te voeren op uw EMC Documentum Content Server, koopt u een geschikt hulpprogramma van derden, zoals EMC NetWorker van EMC of CYA SmartRecovery voor EMC Documentum van CYA. De volgende instructies beschrijven de stappen voor het gebruik van EMC NetWorker Module versie 7.2.2.

U hebt de volgende EMC NetWorker-modules nodig:

* NetWorker-module
* Wizard Configuratie NetWorker
* Wizard Configuratie van NetWorker-apparaat
* De Module van NetWorker voor het gegevensbestandtype dat door uw Server van de Inhoud wordt gebruikt
* NetWorker Module voor Documentum

## De EMC Document Content Server voorbereiden voor back-up en herstel {#preparing-the-emc-document-content-server-for-backup-and-recovery}

In dit gedeelte wordt beschreven hoe u de EMC NetWorker-software op de Content Server kunt installeren en configureren.

**De EMC Documentum-server voorbereiden voor back-up**

1. Installeer op de EMC Documentum Content Server de EMC NetWorker-modules en accepteer alle standaardinstellingen.

   Tijdens de installatieprocessen, wordt u ertoe aangezet om de servernaam van de computer van de Server van de Inhoud als in te gaan *NetWorker-servernaam*. Wanneer u de EMC NetWorker Module voor uw database installeert, kiest u een volledige installatie.

1. Maak met behulp van de onderstaande voorbeeldinhoud een configuratiebestand met de naam *nsrnmd_win.cfg* en sla deze op een toegankelijke locatie op de Content Server op. Dit bestand wordt aangeroepen door de opdrachten voor back-up en herstel.

   De volgende tekst bevat opmaaktekens voor regeleinden. Als u deze tekst naar een locatie buiten dit document kopieert, kopieert u een gedeelte per keer en verwijdert u de opmaaktekens wanneer u deze op de nieuwe locatie plakt.

   ```as3
    ################################################ 
    # NetWorker Module for Documentum v1.2 nsrnmd_win.cfg D5.3+ example with 
    # typical set of working parameters.  THIS FILE MUST BE SITE-CUSTOMISED. 
    # 
    # Parameters not shown can be set in this file (as per site customisation) #or from the command-line. 
    # 
    # Please refer to the user Guides for details on all parameters, including  
    # those not listed below. 
    # Note: DCTM environment for D6 is slightly different from D5, refer to D6 
    # Installation Guide to update the values. 
    ################################################ 
    #Can get values for most of below from doing as the dctm inst owner: cmd> set DOCUMENTUM=C:\Documentum 
    DM_HOME=C:\Documentum\product\6.0 
    JAVA_HOME=C:\Progra~1\Documentum\java\1.5.0_12 
    JAVA_PATH=C:\Progra~1\Documentum\java\1.5.0_12\bin 
    PATH=C:\WINNT\system32;C:\WINNT;C:\WINNT\system32\WBEM;C:\Documentum\product\6.0\bin;C:\Documentum\fulltext\fast;C:\Documentum\product\6.0\fusion;C:\Program Files\Documentum\Shared;C:\Program Files\Legato\nsr\bin;C:\Program Files\Microsoft SQL Server\80\Tools\Binn;C:\Program Files\Microsoft SQL Server\90\DTS\Binn\;C:\Program Files\Microsoft SQL Server\90\Tools\binn;C:\Program Files\Microsoft SQL Server\90\Tools\Binn\VSShell\Common7\IDE;C:\Program Files\Documentum\java\1.5.0_12\bin;C:\Documentum\config;C:\Documentum 
    #See also manifest dctm.jar file for class path locations 
    CLASSPATH=.;C:\Program Files\Legato\nsr\bin;C:\Program Files\Legato\nsr\bin\nsrnmdde.jar;C:\Program Files\Documentum\java\1.5.0_12\lib\tools.jar;C:\Program Files\Documentum\Shared\dfc.jar;C:\Program Files\Documentum\Shared\aspectjrt.jar;C:\Program Files\Documentum\dctm.jar;C:\Program Files\Documentum\Shared\workflow.jar;C:\Program Files\Documentum\Shared\log4j.jar;C:\Program Files\Documentum\java\1.5.0_12\lib\dt.jar;C:\Documentum\config 
     
    ################################################ 
    #If not using nsrnmdsv -m ALL|DB|DB_LOG|FTI|FTI_ALL|ICF|SA|SA_ALL, set #for backup 
    NMD_SCOPE=ALL 
    #Mandatory when scope (backup or restore) is FTI/SA without -a option 
    #NMD_OBJECT_NAME=filestore_01 
    ################################################ 
    NMDDE_DM_DOCBASE=Docbase 
    NMDDE_DM_USER=Administrator 
    #NMDDE_DM_PASSWD must be set via running: nsrnmdsv -f <nmdcfg> -P <pwd>. 
    ################################################ 
    #DB related hooks to invoke arbitrary scripts: 
    #Set if DB is on a remote host 
    #NMD_DB_HOST=dbhost 
    #Pure basename implies remote host execution; absolute path ... local 
    #execution as in NMD v1.0. 
    # 
    #Remote execution requires script be put in remote nsrexecd bin directory 
    #and D5.3+ host be added to remote nsr\res\servers file w/ nsrexecd recycled 
    # 
    #Refer to user Guides for sample script code. 
    NMD_DB_FULL_BACKUP_CMD=C:\DocumentumBackup\Scripts\nsrnmddbf.bat 
    NMD_DB_LOG_BACKUP_CMD=C:\DocumentumBackup\Scripts\nsrnmddbl.bat 
    NMD_DB_INCR_BACKUP_CMD=C:\DocumentumBackup\Scripts\nsrnmddbi.bat 
    ################################################ 
    #For D5.3+ only: NMD_FTI_INCLUDED, NMD_FTI_HOST, NMD_FTI_USER, 
    #NMD_FTI_PASSWD & NMD_FTI_SUBDIRS. 
    #Optional for remote D5.3+ FTI server 
    NMD_FTI_INCLUDED=no 
    #NMD_FTI_HOST=ftihost 
    #Recommended for D5.3+ FTI server quiesce/unquiesce 
    #NMD_FTI_USER=ftiadmin 
    #The index name: optional for D5.3+ FTI server, used with -M FTI_ALL or 
    #-M ALL   
    #NMD_FTI_NAME=rep_name_ftindex_01 
    #Recommended for D5.3+ FTI server quiesce/unquiesce 
    #NMDDE_FTI_PASSWD must be set via running: nsrnmdsv -f <nmdcfg> -P <pwd> 
    #-M FTI. 
    #Pure basename implies remote host execution; absolute path ... local execution 
    #as in NMD v1.0. 
    # 
    #Remote execution requires script be put in remote nsrexecd bin directory 
    #and D5.3+ host be added to remote nsr\res\servers file w/ nsrexecd  
    #recycled. 
    # 
    #See example nsrnmdfti*.bat examples. 
    # 
    #Mandatory for D5.3+ 
    #NMD_BACKUP_FTI_QUIESCE=nsrnmdftiq.bat 
    #NMD_BACKUP_FTI_UNQUIESCE=nsrnmdftiu.bat 
    #Used for D5.3+ to get InstallProfile.xml FTI file in multinode 
    #discovery. 
    #Optional, if not specified, will treat as single-node FTI. 
    #NMD_FTI_GET_INSTPROF=nsrnmdfti_instprof.bat 
    #Mandatory for D5.3+. No spaces in paths or around comma separators. 
    #For remote FTI, paths must be valid at the FTI host. 
    #NMD_FTI_SUBDIRS=F:\Documentum_idx\data\fulltext\fixml,F:\Documentum_idx 
    #\data\fulltext\index 
    ################################################ 
    #Mandatory. No spaces in paths or before comma 
    #separators in NMD_ICF_SUBDIRS_xxx: 
    #NMD_ICF_INCLUDED=yes 
    #NMD_ICF_SUBDIRS=C:\Documentum\dba,C:\Documentum\product\5.3 
    ################################################ 
    NMD_FILEREPORT_INCLUDED=yes 
    NMDDE_METADATA_OUTPUT_DEST=C:\docbase_freports\ 
    ################################################ 
    #Other misc recommended NMD_xxx parameters 
    #Recommended to get more meaningful saveset names 
    NMD_USE_DEFAULT_SAVESET_NAMES=yes 
    #Use following to skip unwanted ICF, FTI and non-SnapImage SA dirs/files. 
    #For example, "<</>> +skip: dm_ftwork_dir" line will skip non-data 
    #files. 
    # 
    #The path will be the same and must exist on D5.3+, remote FTI host, and 
    #RCS hosts correspondingly if used. 
    #NMD_DIRECTIVES_FILE=E:\Program Files\Legato\nsr\res\nsrnmddirectives.txt 
    #For non-SnapImage SA backup 
    #NMD_SA_FULL_NUM_SAVESET=16 
    #NMD_SA_INCR_NUM_SAVESET=4 
    #NMD_USE_SNAPIMAGE=yes 
    ################################################ 
    # DSA setup 
    ################################################ 
    # Name of the config file at the remote sites; 
    # Mandatory, listed in the config file at the primary host. 
    # (if skipped, backup is treated as local) 
    # NMD_RCS_CFG_FILE=rep_name_rcs.cfg 
     
    # SA-host mapping add, optional, will override far-store list info. 
    # No space around comma. 
    # NMD_HOST_SAS_MAP=host01,sa_01,sa_02 
    # NMD_HOST_SAS_MAP=host02,sa_03 
    ################################################ 
    NSR_SERVER=con-dctm 
    #NSR_CLIENT=d5svrhost 
    NSR_GROUP=Default 
    NSR_DATA_VOLUME_POOL=Default 
    #NSR_SNAPIMAGE_DATA_VOLUME_POOL=Default 
    #Relocation dir will be the same on D5+ and remote FTI/SA hosts. 
    NSR_RELOCATION=C:\reloc 
    #NSR_PARALLELISM=16 
    NSR_DEBUG_FILE=C:\Program Files\Legato\nsr\applogs\nmd.log 
    NSR_DEBUG_LEVEL=9 
    ################################################ 
    NMDDE_DM_PASSWD=XAtup9pl
   ```

   Het wachtwoordveld voor het configuratiebestand behouden `NMDDE_DM_PASSWD` leeg. In de volgende stap stelt u het wachtwoord in.

1. Stel het wachtwoord voor het configuratiebestand als volgt in:

   * Een opdrachtprompt openen en wijzigen in *[NetWorker_root]*\Legato\nsr\bin.
   * Voer de volgende opdracht uit: `-nsrnmdsv.exe -f`*&lt;path_to_cfg_file> -P &lt;password>*

1. Maak de uitvoerbare batchbestanden (.bat) die worden gebruikt om een back-up van de database te maken. (Zie de documentatie van NetWorker.) Stel de details in de batchbestanden in op basis van uw installatie.

   * Volledige back-up van database (nsrnmddbf.bat):

      *[NetWorker_database_module_root]* `-s`*&lt;networker_server_name>* `-U`*[gebruikersnaam ]*`-P`*[password]* `-l full`*&lt;database_name>*

   * Incrementele back-up van databases (nsrnmddbi.bat):

      *[NetWorker_database_module_root]* `-s`*&lt;networker_server_name>* `-U`*[gebruikersnaam ]*`-P`*[password]* `-l 1 -R`*&lt;database_name>*

   * Back-up van databaselogbestand (nsrnmddbl.bat):

      *[NetWorker_database_module_root]* `-s`*&lt;networker_server_name>* `-U`*[gebruikersnaam ]*`-P`*[password]* `-l incr -R`*&lt;database_name>*

      Waar:

      `[NetWorker_database_module_root]` is de installatiemap van de module NetWorker. Bijvoorbeeld, is de standaardinstallatiemap voor Module NetWorker voor SQL Server C:\Program Files\Legato\nsr\bin\nsrsqlsv.

      `NetWorker_Server_Name` is de server waarop NetWorker is geïnstalleerd.

      `username` &amp; `password` Dit zijn de gebruikersnaam en het wachtwoord van de databasebeheerder.

      `database_name` is de naam van de database waarvan een back-up moet worden gemaakt.

**Een back-upapparaat maken**

1. Maak een nieuwe directory op de EMC Documentum-server en deel de map door alle gebruikers volledige rechten te geven.
1. Start EMC NetWorker Administrator en klik op Mediabeheer > Apparaten.
1. Klik met de rechtermuisknop op Apparaten en selecteer Maken.
1. Voer de volgende waarden in en klik op OK:

   **Naam:** Het volledige pad van de gedeelde map

   **Mediatype:** `File`

1. Klik met de rechtermuisknop op het nieuwe apparaat en selecteer Bewerkingen.
1. Klik op Label, voer een naam in, klik op OK en klik op Onderbrengen.

Er wordt een apparaat toegevoegd waarop de back-upbestanden worden opgeslagen. U kunt meerdere apparaten met verschillende indelingen toevoegen.

## Back-up maken van de EMC Documentum Content Server {#back-up-the-emc-documentum-content-server}

Voer de volgende taken uit nadat u een volledige back-up van uw AEM formuliergegevens hebt gemaakt. (Zie [Back-ups maken van de AEM formuliergegevens](/help/forms/using/admin-help/backing-aem-forms-data.md#backing-up-the-aem-forms-data).)

>[!NOTE]
>
>De bevelmanuscripten vereisen de volledige weg aan het nsrnmd_win.cfg- dossier dat u in creeerde [De EMC Document Content Server voorbereiden voor back-up en herstel](backing-recovering-emc-documentum-repository.md#preparing-the-emc-document-content-server-for-backup-and-recovery).

1. Een opdrachtprompt openen en wijzigen in *[NetWorker_root]*\Legato\nsr\bin.
1. Voer de volgende opdracht uit:

   ```as3
    - nsrnmdsv.exe -f <path_to_cfg_file>
   ```

## De EMC Documentum Content Server herstellen {#restore-the-emc-documentum-content-server}

Voer de volgende taken uit voordat u de AEM formuliergegevens herstelt. (Zie [De AEM formuliergegevens herstellen](/help/forms/using/admin-help/recovering-aem-forms-data.md#recovering-the-aem-forms-data).)

>[!NOTE]
>
>De bevelmanuscripten vereisen de volledige weg aan het nsrnmd_win.cfg- dossier dat u in creeerde [De EMC Document Content Server voorbereiden voor back-up en herstel](backing-recovering-emc-documentum-repository.md#preparing-the-emc-document-content-server-for-backup-and-recovery).

1. Stop de Docbase-service die u wilt herstellen.
1. Start het hulpprogramma NetWorker-gebruiker voor uw databasemodule (bijvoorbeeld *NetWorker-gebruiker voor SQL Server*).
1. Klik op het gereedschap Herstellen en selecteer vervolgens Normaal.
1. Selecteer links in het scherm de database voor uw Docbase en klik op de knop Start op de werkbalk.
1. Start de Docbase-service opnieuw wanneer de database is hersteld.
1. Een opdrachtprompt openen en wijzigen in *[NetWorker_root]*\Legato\nsr\bin
1. Voer de volgende opdracht uit:

   ```as3
    - nsrnmdrs.exe -B <docbase_name> -f <path_to_cfg_file> -C SA
   ```
