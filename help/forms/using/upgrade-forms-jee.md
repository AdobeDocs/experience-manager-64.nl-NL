---
title: Upgrade naar AEM 6.4 Forms
seo-title: Upgrade naar AEM 6.4 Forms
description: 'U kunt een directe verbetering van AEM 6.1 Forms, AEM 6.2 Forms, en LiveCycle ES4 SP1 aan AEM 6.3 Forms uitvoeren. '
seo-description: 'U kunt een directe verbetering van AEM 6.1 Forms, AEM 6.2 Forms, en LiveCycle ES4 SP1 aan AEM 6.3 Forms uitvoeren. '
uuid: 1435246a-9215-4d88-b52c-59a5c329bb77
content-type: reference
products: SG_EXPERIENCEMANAGER/6.3/FORMS
topic-tags: installing
geptopics: SG_AEMFORMS/categories/jee
discoiquuid: e745033f-8015-4fae-9d82-99d35802c0a6
role: Beheerder
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '1679'
ht-degree: 0%

---


# Upgrade naar AEM 6.4 Forms op JEE {#upgrade-to-aem-forms-jee}

Gebruik een van de volgende upgradepaden, al naar gelang uw omgeving.

## AEM 6.2 Forms in JEE of AEM 6.3 Forms in JEE > AEM 6.4 Forms in JEE {#aem-forms-jee-62-63-to-64}

Voer de volgende procedure uit om bestaande AEM 6.2 Forms op JEE of AEM 6.3 Forms op JEE aan AEM 6.4 Forms op JEE te bevorderen:

1. Download de AEM 6.4 Forms op het JEE-installatieprogramma van de [Adobe Licensing Website (LWS)](https://licensing.adobe.com/). U hebt een geldig onderhouds- en ondersteuningscontract nodig om het installatieprogramma te downloaden.
1. Zie [Controlelijst voor upgrades en planning](https://www.adobe.com/go/learn_aemfroms_upgrade_checklist_63) voor meer informatie over de controles die moeten worden uitgevoerd om een geslaagde upgrade te garanderen.
1. Zie [Voorbereiden op upgrade naar AEM Forms](https://www.adobe.com/go/learn_aemforms_prepareupgrade_63) om de taken te leren en uit te voeren die ervoor zorgen dat de upgrade correct wordt uitgevoerd met minimale serverdowntime.
1. Afhankelijk van uw bestaande omgeving en toepassingsserver kiest u een van de volgende documenten en volgt u de instructies.

   * [Upgrade van AEM 6.2 of AEM 6.3 Forms naar AEM 6.4 Forms voor JBoss](assets/upgrade-jboss.pdf)
   * [Upgrade van AEM 6.2 of AEM 6.3 Forms naar AEM 6.4 Forms for WebLogic](assets/upgrade-weblogic.pdf)
   * [Upgrade van AEM 6.2 of AEM 6.3 Forms naar AEM 6.4 Forms for WebSphere](assets/upgrade-websphere.pdf)
   * [Upgrade van AEM 6.2 of AEM 6.3 Forms naar AEM 6.4 Forms voor JBoss Turnkey](assets/upgrade-turnkey.pdf)

## AEM 6.0 Forms op JEE > AEM 6.3 Forms op JEE {#aem-forms-jee-60-to-63}

Directe upgrade van LiveCycle ES2, LiveCycle ES3, AEM 6.0 Forms, AEM 6.1 Forms naar AEM 6.4 Forms is niet beschikbaar. U kunt een tussentijdse upgrade uitvoeren naar een of meer versies van LiveCycle of AEM Forms en vervolgens een upgrade uitvoeren vanaf AEM 6.4 Forms. Voor de lijst van tussenliggende versies en overeenkomstige verbeteringsinstructies, zie [Kies een verbeteringspad](upgrade.md).

## LiveCycle ES4 SP1 > AEM 6.4 Forms op JEE {#livecycle-es4sp1-forms-jee}

De verbetering van LiveCycle ES4 SP1 aan AEM 6.4 Forms op JEE is een verouderd verbetering, aangezien het het migreren van activa en gegevens van vorige versies aan de nieuwe instanties (nieuwe versies) van gesteunde toepassingsservers, werkende systemen, en gegevensbestanden impliceert.

Hier volgt een overzicht van de procedure voor het upgraden van een bestaande LiveCycle ES4 SP1-server naar AEM 6.4 Forms. Zie voor gedetailleerde instructies de documenten die aan het einde van de procedure worden weergegeven.

1. Voordat u een upgrade uitvoert:

   1. Download de AEM 6.4 Forms op het JEE-installatieprogramma van de [Adobe Licensing Website (LWS)](https://licensing.adobe.com/). U hebt een geldig onderhouds- en ondersteuningscontract nodig om het installatieprogramma te downloaden.
   1. Bepaal het type gegevensopslagruimte (CRX Repository) voor inhoud dat u wilt gebruiken. Slechts enkele AEM Forms on JEE-mogelijkheden gebruiken de persistentie van de opslagplaats voor inhoud en middelen. Installeer en configureer de opslagplaats voor inhoud alleen als u dergelijke AEM Forms-mogelijkheden voor JEE wilt gebruiken:

      * In LiveCycle ES4 SP1 gebruiken de Correspondentiebeheerfuncties, Forms Portal, HTML Workspace en Process Reporting-mogelijkheden de opslagplaats voor inhoud. Als u deze mogelijkheden in LiveCycle ES4 niet hebt gebruikt en u van plan bent deze mogelijkheden in AEM Forms niet te gebruiken, is de gegevensopslagruimte niet vereist.
      * In AEM Forms, Adaptive Forms, Correspondence Management, HTML5 Forms (bekend als Mobile Forms in LiveCycle ES4 SP1), Forms Portal, HTML Workspace, Process Reporting, Forms centrische workflows op OSGi, mogelijkheden gebruiken Content Repository. Als u AEM Forms voor deze mogelijkheden wilt gebruiken, is de opslagplaats voor inhoud vereist.
      * U hebt geen opslagplaats voor inhoud nodig voor AEM Forms-documentbeveiliging.

      Bovendien zijn het type opslagplaats van LiveCycle en AEM Forms verschillend. Zie [Een persistentietype kiezen voor een AEM Forms-installatie](/help/forms/using/choosing-persistence-type-for-aem-forms.md) voor informatie over de beschikbare repository typen en gerelateerde informatie.

   1. Maak een back-up van LiveCycle ES4 SP1-inhoud en -gegevens:

      Maak een back-up van de LiveCycle ES4 SP1-database, de Global Data Storage (GDS) en de crx-repository (niet vereist voor documentbeveiliging). Als u aan MongoMK of persistentie RDBMK bevordert, voer LiveCycle ES4 SP1 brievenbeheeractiva in een .cmp- dossier uit en vormt activa als AEM pakket.

   1. Zorg ervoor dat uw bestaande platform (dat wil zeggen toepassingsserver, database, besturingssysteem, Adobe Acrobat, toepassingen van derden en hardware) wordt ondersteund voor AEM 6.4 Forms op JEE. Raadpleeg het document [Supported Platform Combinations](/help/forms/using/aem-forms-jee-supported-platforms.md) voor informatie over ondersteunde hardware en software.

      Als u een nieuw exemplaar van de database maakt, importeert u de gegevens waarvan in stap 3 een back-up is gemaakt in de database. Voor informatie over hoe te om gegevens in een gegevensbestand in te voeren, zie documentatie van overeenkomstige gegevensbestandverkoper.

      >[!NOTE]
      >
      >Als u RDBMK persistence-indeling gebruikt, gebruikt u één database voor zowel de persistentie in de repository als de documentservices die op AEM Forms op JEE worden uitgevoerd.


1. Voer de upgrade uit:

   1. Installeer AEM 6.4 Forms op JEE op een nieuwe server door het installatieprogramma uit te voeren. Het installatieprogramma plaatst alle vereiste bestanden op de computer, binnen één structuur van de installatiemap.
   1. Nadat de installatie volledig is, stel **Manager** van de Configuratie in werking om diverse modules van AEM Forms te vormen en aangewezen configuraties te plaatsen. Samen met het vormen van montages, staat het toe om de weg van Globale Opslag van Gegevens (GDS) en crx-bewaarplaats te specificeren.

      >[!NOTE]
      >
      >Selecteer de optie **[!UICONTROL Upgrade from Adobe Experience Manager Forms 6.2.0]** in het scherm Taakselectie bijwerken. Met de optie **[!UICONTROL Upgrade from Adobe Experience Manager Forms 6.2.0]** kan de configuratiemanager een upgrade uitvoeren van LiveCycle ES4 SP1 naar AEM 6.4 Forms.

   1. (Niet vereist voor AEM Forms-documentbeveiligingsmodule) Inhoud importeren naar de Content Repository (CRX-Repository) naar AEM 6.4 Forms-server.

      >[!NOTE]
      >
      >* Nadat de crx-gegevensopslagruimte is bijgewerkt en de inhoud is gemigreerd, wijzigt u het wachtwoord van de beheerdersaccount. Voor gedetailleerde instructies, zie [Veranderend het Wachtwoord voor een Bestaande Gebruiker ](/help/sites-administering/granite-user-group-admin.md).


1. Voer de post-plaatsingstaken uit om login geloofsbrieven te verifiëren, documentdiensten, correspondentiebeheer, documentveiligheid, en meer afhankelijk van uw gebruiksgeval te vormen.
1. Controleer of de upgrade van de server is geslaagd:

   Voer een aantal routinebewerkingen uit op de geüpgrade AEM Forms-server om ervoor te zorgen dat de upgrade van de server is voltooid. U kunt enkele gemigreerde formulieren invullen en verzenden of documenten beveiligen voor een geslaagde upgrade.

   >[!NOTE]
   >
   >In AEM 6.4 Forms is de structuur van crx-repository veranderd. Nadat u een upgrade hebt uitgevoerd naar AEM 6.4-formulieren, gebruikt u de gewijzigde paden voor aanpassing die u opnieuw maakt. Zie [Herstructurering van de opslagplaats in Forms in AEM 6.4](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md) voor de volledige lijst met gewijzigde paden.

**Afhankelijk van uw bestaande omgeving en toepassingsserver kiest u een van de volgende documenten en volgt u de gedetailleerde instructies:**

* [Upgrade van LiveCycle ES4 SP1 naar AEM 6.4 Forms voor JBoss](assets/upgrade-jboss-livecycle.pdf)
* [Upgrade van LiveCycle ES4 SP1 naar AEM 6.4 Forms for WebLogic](assets/upgrade-weblogic-livecycle.pdf)
* [Upgrade van LiveCycle ES4 SP1 naar AEM 6.4 Forms for WebSphere](assets/upgrade-websphere-livecycle.pdf)
* [Upgrade van LiveCycle ES4 SP1 naar AEM 6.4 Forms met JBoss Turnkey](assets/upgrade-turnkey-livecycle.pdf)

<!--Theses sections used to be an accordion until converted to straight Markdown. When accordions are enabled, revert-->

## LiveCycle ES3 > AEM 6.4 Forms op JEE {#livecycle-es3-forms-jee}

De verbetering van LiveCycle ES3 aan AEM 6.4 Forms op JEE is een verouderde verbetering, aangezien het het migreren van activa en gegevens van vorige versies aan de nieuwe instanties (nieuwe versies) van gesteunde toepassingsservers, werkende systemen, en gegevensbestanden impliceert.

Hier volgt een overzicht van de procedure voor het upgraden van een bestaande LiveCycle ES3-server naar AEM 6.4 Forms. Zie voor gedetailleerde instructies de documenten die aan het einde van de procedure worden weergegeven.

1. Voordat u een upgrade uitvoert:

   1. Download de AEM 6.4 Forms op het JEE-installatieprogramma van de [Adobe Licensing Website (LWS)](https://licensing.adobe.com/). U hebt een geldig onderhouds- en ondersteuningscontract nodig om het installatieprogramma te downloaden.
   1. Bepaal het type gegevensopslagruimte (CRX Repository) voor inhoud dat u wilt gebruiken. Slechts enkele AEM Forms on JEE-mogelijkheden gebruiken de persistentie van de opslagplaats voor inhoud en middelen. Installeer en configureer de opslagplaats voor inhoud alleen als u dergelijke AEM Forms-mogelijkheden voor JEE wilt gebruiken:

      * In AEM Forms gebruiken Adaptive Forms, Correspondence Management, HTML5 Forms, Forms Portal, HTML Workspace, Process Reporting en Forms centric workflows op OSGi-mogelijkheden de Content Repository. Als u AEM Forms voor deze mogelijkheden wilt gebruiken, is de opslagplaats voor inhoud vereist.
      * U hebt geen opslagplaats voor inhoud nodig voor AEM Forms-documentbeveiliging.

      Bovendien zijn het type opslagplaats van LiveCycle en AEM Forms verschillend. Zie [Een persistentietype kiezen voor een AEM Forms-installatie](/help/forms/using/choosing-persistence-type-for-aem-forms.md) voor informatie over de beschikbare repository typen en gerelateerde informatie.

   1. Maak een back-up van de LiveCycle ES3-database, de Global Data Storage (GDS) en de Content Repository (niet vereist voor documentbeveiliging). Als u aan MongoMK of persistentie RDBMK bevordert, voer LiveCycle ES3 brievenbeheeractiva als archief uit.
   1. Zorg ervoor dat uw bestaande platform (dat wil zeggen toepassingsserver, database, besturingssysteem, Adobe Acrobat, toepassingen van derden en hardware) wordt ondersteund voor AEM 6.4 Forms op JEE. Raadpleeg het document [Supported Platform Combinations](/help/forms/using/aem-forms-jee-supported-platforms.md) voor informatie over ondersteunde hardware en software.

      Als u een nieuw exemplaar van de database maakt, importeert u de gegevens waarvan in stap 3 een back-up is gemaakt in de database. Voor informatie over hoe te om gegevens in een gegevensbestand in te voeren, zie documentatie van overeenkomstige gegevensbestandverkoper.

      >[!NOTE]
      >
      >Als u RDBMK persistence-indeling gebruikt, gebruikt u één database voor zowel de persistentie van de opslagruimte als documentservices die op AEM Forms op JEE worden uitgevoerd.


1. Voer de upgrade uit:

   1. Installeer AEM 6.4 Forms op JEE op een nieuwe server door het installatieprogramma uit te voeren. Het installatieprogramma plaatst alle vereiste bestanden op de computer, binnen één structuur van de installatiemap.
   1. Nadat de installatie volledig is, stel **Manager** van de Configuratie in werking om diverse modules van AEM Forms te vormen en aangewezen configuraties te plaatsen. Samen met het vormen van montages, staat het toe om de weg van Globale Opslag van Gegevens (GDS) en crx-bewaarplaats te specificeren.

      >[!NOTE]
      >
      >Selecteer de optie **[!UICONTROL Upgrade from Adobe Experience Manager Forms 6.2.0]** in het scherm Taakselectie bijwerken. Met de optie **[!UICONTROL Upgrade from Adobe Experience Manager Forms 6.2.0]** kan de configuratiemanager een upgrade uitvoeren van LiveCycle ES3 naar AEM 6.4 Forms.

   1. (Niet vereist voor AEM Forms-documentbeveiligingsmodule) Voer een upgrade uit en importeer de CRX-opslagruimte naar AEM 6.4 Forms-server.

      >[!NOTE]
      >
      >Nadat de crx-gegevensopslagruimte is bijgewerkt en de inhoud is gemigreerd, wijzigt u het wachtwoord van de beheerdersaccount. Voor gedetailleerde instructies, zie [Veranderend het Wachtwoord voor een Bestaande Gebruiker ](/help/sites-administering/granite-user-group-admin.md).
1. Voer de post-plaatsingstaken uit om login geloofsbrieven te verifiëren, documentdiensten, correspondentiebeheer, documentveiligheid, en meer afhankelijk van uw gebruiksgeval te vormen.
1. Controleer of de upgrade van de server is geslaagd:

   Voer een aantal routinebewerkingen uit op de geüpgrade AEM Forms-server om ervoor te zorgen dat de upgrade van de server is voltooid. U kunt enkele gemigreerde formulieren invullen en verzenden of documenten beveiligen voor een geslaagde upgrade.

   >[!NOTE]
   >
   >In AEM 6.4 Forms is de structuur van crx-repository veranderd. Nadat u een upgrade hebt uitgevoerd naar AEM 6.4-formulieren, gebruikt u de gewijzigde paden voor aanpassing die u opnieuw maakt. Zie [Herstructurering van de opslagplaats in Forms in AEM 6.4](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md) voor de volledige lijst met gewijzigde paden.

**Afhankelijk van uw bestaande omgeving en toepassingsserver kiest u een van de volgende documenten en volgt u de gedetailleerde instructies:**

* [Upgrade van LiveCycle ES3 naar AEM 6.4 Forms voor JBoss](assets/upgrade-jboss-livecycle-es3.pdf)
* [Upgrade van LiveCycle ES3 naar AEM 6.4 Forms for WebLogic](assets/upgrade-weblogic-livecycle-es3.pdf)
* [Upgrade van LiveCycle ES3 naar AEM 6.4 Forms for WebSphere](assets/upgrade-websphere-livecycle-es3.pdf)
* [Upgrade van LiveCycle ES3 naar AEM 6.4 Forms met JBoss Turnkey](assets/upgrade-turnkey-livecycle-es3.pdf)
