---
title: Upgrade naar AEM 6.4-formulieren
seo-title: Upgrade naar AEM 6.4-formulieren
description: 'U kunt een directe upgrade uitvoeren van AEM 6.1-formulieren, AEM 6.2-formulieren en LiveCycle ES4 SP1 naar AEM 6.3-formulieren. '
seo-description: 'U kunt een directe upgrade uitvoeren van AEM 6.1-formulieren, AEM 6.2-formulieren en LiveCycle ES4 SP1 naar AEM 6.3-formulieren. '
uuid: 1435246a-9215-4d88-b52c-59a5c329bb77
content-type: reference
products: SG_EXPERIENCEMANAGER/6.3/FORMS
topic-tags: installing
geptopics: SG_AEMFORMS/categories/jee
discoiquuid: e745033f-8015-4fae-9d82-99d35802c0a6
translation-type: tm+mt
source-git-commit: d2657bc364b7a814fac9228afdec60f96faaf175

---


# Upgrade naar AEM 6.4-formulieren in JEE {#upgrade-to-aem-forms-jee}

Gebruik een van de volgende upgradepaden, al naar gelang uw omgeving.

## AEM 6.2 Forms on JEE, of AEM 6.3 Forms on JEE > AEM 6.4 Forms on JEE {#aem-forms-jee-62-63-to-64}

Voer de volgende procedure uit om bestaande Vormen AEM 6.2 op JEE of AEM 6.3 Vormen op JEE aan Vormen AEM 6.4 op JEE te bevorderen:

1. Download AEM 6.4 Forms in het JEE-installatieprogramma van de [Adobe-licentiewebsite (LWS)](https://licensing.adobe.com/). U hebt een geldig onderhouds- en ondersteuningscontract nodig om het installatieprogramma te downloaden.
1. Zie Controlelijst voor [upgraden en planning](https://www.adobe.com/go/learn_aemfroms_upgrade_checklist_63) voor meer informatie over de controles die moeten worden uitgevoerd om een geslaagde upgrade te garanderen.
1. Zie [Voorbereiden op upgrade naar AEM Forms](https://www.adobe.com/go/learn_aemforms_prepareupgrade_63) om de taken te leren en uit te voeren die ervoor zorgen dat de upgrade correct wordt uitgevoerd met minimale downtime op de server.
1. Afhankelijk van uw bestaande omgeving en toepassingsserver kiest u een van de volgende documenten en volgt u de instructies.

   * [Upgrade van AEM 6.2- of AEM 6.3-formulieren naar AEM 6.4-formulieren voor JBoss](assets/upgrade-jboss.pdf)
   * [Upgrade van AEM 6.2- of AEM 6.3-formulieren naar AEM 6.4-formulieren voor WebLogic](assets/upgrade-weblogic.pdf)
   * [Upgrade van AEM 6.2- of AEM 6.3-formulieren naar AEM 6.4-formulieren voor WebSphere](assets/upgrade-websphere.pdf)
   * [Upgrade van AEM 6.2- of AEM 6.3-formulieren naar AEM 6.4-formulieren voor JBoss Turnkey](assets/upgrade-turnkey.pdf)

## AEM 6.0 Forms on JEE > AEM 6.3 Forms on JEE {#aem-forms-jee-60-to-63}

Er is geen directe upgrade beschikbaar van LiveCycle ES2, LiveCycle ES3, AEM 6.0 Forms en AEM 6.1 Forms naar AEM 6.4 Forms. U kunt een tussentijdse upgrade uitvoeren naar een of meer versies van LiveCycle of AEM Forms en vervolgens een upgrade uitvoeren vanaf AEM 6.4 Forms. Voor de lijst van tussenliggende versies en overeenkomstige verbeteringsinstructies, zie een [verbeteringspad](/help/forms/using/upgrade.md#main-pars-header)kiezen.

## LiveCycle ES4 SP1 > AEM 6.4 Forms on JEE {#livecycle-es4sp1-forms-jee}

De upgrade van LiveCycle ES4 SP1 naar AEM 6.4 Forms op JEE is een externe upgrade omdat hierbij elementen en gegevens uit vorige versies naar de nieuwe exemplaren (nieuwe versies) van ondersteunde toepassingsservers, besturingssystemen en databases worden gemigreerd.

Hieronder volgt een overzicht van de procedure voor het upgraden van een bestaande LiveCycle ES4 SP1-server naar AEM 6.4 Forms. Zie voor gedetailleerde instructies de documenten die aan het einde van de procedure worden weergegeven.

1. Voordat u een upgrade uitvoert:

   1. Download AEM 6.4 Forms in het JEE-installatieprogramma van de [Adobe-licentiewebsite (LWS)](https://licensing.adobe.com/). U hebt een geldig onderhouds- en ondersteuningscontract nodig om het installatieprogramma te downloaden.
   1. Bepaal het type gegevensopslagruimte (CRX Repository) voor inhoud dat u wilt gebruiken. Slechts enkele AEM Forms on JEE-mogelijkheden gebruiken de persistentie van de opslagplaats voor inhoud en elementen. Installeer en configureer de opslagplaats voor inhoud alleen als u dergelijke AEM-formulieren op JEE-mogelijkheden wilt gebruiken:

      * In LiveCycle ES4 SP1 gebruiken de mogelijkheden Correspondentiebeheer, Forms Portal, HTML Workspace en Process Reporting de functie Inhoudsopslagplaats. Als u deze mogelijkheden niet hebt gebruikt in LiveCycle ES4 en u van plan bent deze mogelijkheden niet te gebruiken in AEM Forms, is Inhoudsopslag niet vereist.
      * In AEM-formulieren, Adaptive Forms, Correspondence Management, HTML5-formulieren (ook wel mobiele formulieren genoemd in LiveCycle ES4 SP1), Forms Portal, HTML-werkruimte, Process Reporting, Forms centric workflows op OSGi, capabilities gebruik Content Repository. Als u van plan bent AEM Forms voor deze mogelijkheden te gebruiken, dan wordt de Bewaarplaats van de Inhoud vereist.
      * U hebt geen opslagplaats voor inhoud nodig voor documentbeveiliging in AEM Forms.
      Bovendien zijn het type opslagplaats van LiveCycle en AEM Forms verschillend. Zie Een persistentietype [kiezen voor een AEM Forms-installatie](/help/forms/using/choosing-persistence-type-for-aem-forms.md)voor informatie over beschikbare typen opslagruimten en verwante informatie.

   1. Maak een back-up van LiveCycle ES4 SP1-inhoud en -gegevens:

      Maak een back-up van de LiveCycle ES4 SP1-database, de Global Data Storage (GDS) en de crx-gegevensopslagruimte (niet vereist voor documentbeveiliging). Als u een upgrade uitvoert naar MongoMK of RDBMK-persistentie, exporteert u LiveCycle ES4 SP1-middelen voor correspondentiebeheer in een .cmp-bestand en vormt u elementen als een AEM-pakket.

   1. Zorg ervoor dat uw bestaande platform (dat wil zeggen toepassingsserver, database, besturingssysteem, Adobe Acrobat, toepassingen van derden en hardware) wordt ondersteund voor AEM 6.4 Forms op JEE. Raadpleeg het document [Ondersteunde platformcombinaties](/help/forms/using/aem-forms-jee-supported-platforms.md) voor informatie over ondersteunde hardware en software.

      Als u een nieuw exemplaar van de database maakt, importeert u de gegevens waarvan in stap 3 een back-up is gemaakt in de database. Voor informatie over hoe te om gegevens in een gegevensbestand in te voeren, zie documentatie van overeenkomstige gegevensbestandverkoper.

      >[!NOTE]
      >
      >Als u RDBMK persistence-indeling gebruikt, gebruikt u één database voor zowel de persistentie in de opslagruimte als de documentservices die op AEM Forms on JEE worden uitgevoerd.


1. Voer de upgrade uit:

   1. Installeer AEM 6.4 Forms op JEE op een nieuwe server door het installatieprogramma uit te voeren. Het installatieprogramma plaatst alle vereiste bestanden op de computer, binnen één structuur van de installatiemap.
   1. Nadat de installatie volledig is, stel de Manager **van de** Configuratie in werking om diverse modules van Vormen AEM te vormen en aangewezen configuraties te plaatsen. Samen met het vormen van montages, staat het toe om de weg van Globale Opslag van Gegevens (GDS) en crx-bewaarplaats te specificeren.

      >[!NOTE]
      >
      >Selecteer in het scherm Taakselectie bijwerken de optie **[!UICONTROL Upgrade uitvoeren in Adobe Experience Manager Forms 6.2.0]** . Met de optie **[!UICONTROL Upgrade uitvoeren vanuit Adobe Experience Manager Forms 6.2.0]** kan de configuratiemanager een upgrade uitvoeren van LiveCycle ES4 SP1 naar AEM 6.4 Forms.

   1. (Niet vereist voor de beveiligingsmodule van AEM Forms-document) Inhoud importeren naar de opslagplaats voor inhoud (CRX-Repository) naar de server voor AEM 6.4-formulieren.

      >[!NOTE]
      >
      >* Nadat de crx-gegevensopslagruimte is bijgewerkt en de inhoud is gemigreerd, wijzigt u het wachtwoord van de beheerdersaccount. Zie Het wachtwoord [wijzigen voor een bestaande gebruiker](/help/sites-administering/granite-user-group-admin.md)voor gedetailleerde instructies.


1. Voer de post-plaatsingstaken uit om login geloofsbrieven te verifiëren, documentdiensten, correspondentiebeheer, documentveiligheid, en meer afhankelijk van uw gebruiksgeval te vormen.
1. Controleer of de upgrade van de server is geslaagd:

   Voer een aantal routinebewerkingen uit op de geüpgrade AEM Forms-server om ervoor te zorgen dat de server correct is bijgewerkt. U kunt enkele gemigreerde formulieren invullen en verzenden of documenten beveiligen voor een geslaagde upgrade.

   >[!NOTE]
   >
   >In AEM 6.4 Forms is de structuur van crx-gegevensopslagruimte gewijzigd. Nadat u een upgrade naar AEM 6.4-formulieren hebt uitgevoerd, gebruikt u de gewijzigde paden voor aanpassing die u opnieuw maakt. Zie [Forms Repository Reform in AEM 6.4 voor een volledige lijst met gewijzigde paden](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md).

**Afhankelijk van uw bestaande omgeving en toepassingsserver kiest u een van de volgende documenten en volgt u de gedetailleerde instructies:**

* [Upgrade van LiveCycle ES4 SP1 naar AEM 6.4-formulieren voor JBoss](assets/upgrade-jboss-livecycle.pdf)
* [Upgrade van LiveCycle ES4 SP1 naar AEM 6.4 Forms for WebLogic](assets/upgrade-weblogic-livecycle.pdf)
* [Upgrade van LiveCycle ES4 SP1 naar AEM 6.4 Forms for WebSphere](assets/upgrade-websphere-livecycle.pdf)
* [Upgrade van LiveCycle ES4 SP1 naar AEM 6.4-formulieren met JBoss Turnkey](assets/upgrade-turnkey-livecycle.pdf)

<!--Theses sections used to be an accordion until converted to straight Markdown. When accordions are enabled, revert-->

## LiveCycle ES3 > AEM 6.4 Forms on JEE {#livecycle-es3-forms-jee}

De upgrade van LiveCycle ES3 naar AEM 6.4 Forms op JEE is een externe upgrade, omdat hierbij elementen en gegevens uit vorige versies worden gemigreerd naar de nieuwe exemplaren (nieuwe versies) van ondersteunde toepassingsservers, besturingssystemen en databases.

Hieronder volgt een overzicht van de procedure voor het upgraden van een bestaande LiveCycle ES3-server naar AEM 6.4 Forms. Zie voor gedetailleerde instructies de documenten die aan het einde van de procedure worden weergegeven.

1. Voordat u een upgrade uitvoert:

   1. Download AEM 6.4 Forms in het JEE-installatieprogramma van de [Adobe-licentiewebsite (LWS)](https://licensing.adobe.com/). U hebt een geldig onderhouds- en ondersteuningscontract nodig om het installatieprogramma te downloaden.
   1. Bepaal het type gegevensopslagruimte (CRX Repository) voor inhoud dat u wilt gebruiken. Slechts enkele AEM Forms on JEE-mogelijkheden gebruiken de persistentie van de opslagplaats voor inhoud en elementen. Installeer en configureer de opslagplaats voor inhoud alleen als u dergelijke AEM-formulieren op JEE-mogelijkheden wilt gebruiken:

      * In AEM-formulieren, adaptieve formulieren, Correspondentiebeheer, HTML5-formulieren, Forms Portal, HTML-werkruimte, Process Reporting en Forms centric workflows op OSGi-mogelijkheden gebruiken Inhoud opslaan. Als u van plan bent AEM Forms voor deze mogelijkheden te gebruiken, dan wordt de Bewaarplaats van de Inhoud vereist.
      * U hebt geen opslagplaats voor inhoud nodig voor documentbeveiliging in AEM Forms.
      Bovendien zijn het type opslagplaats van LiveCycle en AEM Forms verschillend. Zie Een persistentietype [kiezen voor een AEM Forms-installatie](/help/forms/using/choosing-persistence-type-for-aem-forms.md)voor informatie over beschikbare typen opslagruimten en verwante informatie.

   1. Maak een back-up van de LiveCycle ES3-database, de Global Data Storage (GDS) en de Content Repository (niet vereist voor documentbeveiliging). Als u een upgrade uitvoert naar MongoMK- of RDBMK-persistentie, exporteert u LiveCycle ES3-middelen voor correspondentiebeheer als een archief.
   1. Zorg ervoor dat uw bestaande platform (dat wil zeggen toepassingsserver, database, besturingssysteem, Adobe Acrobat, toepassingen van derden en hardware) wordt ondersteund voor AEM 6.4 Forms op JEE. Raadpleeg het document [Ondersteunde platformcombinaties](/help/forms/using/aem-forms-jee-supported-platforms.md) voor informatie over ondersteunde hardware en software.

      Als u een nieuw exemplaar van de database maakt, importeert u de gegevens waarvan in stap 3 een back-up is gemaakt in de database. Voor informatie over hoe te om gegevens in een gegevensbestand in te voeren, zie documentatie van overeenkomstige gegevensbestandverkoper.

      >[!NOTE] Als u RDBMK persistence-indeling gebruikt, gebruikt u één database voor zowel gegevensopslagpersistentie als documentservices die op AEM Forms on JEE worden uitgevoerd.


1. Voer de upgrade uit:

   1. Installeer AEM 6.4 Forms op JEE op een nieuwe server door het installatieprogramma uit te voeren. Het installatieprogramma plaatst alle vereiste bestanden op de computer, binnen één structuur van de installatiemap.
   1. Nadat de installatie volledig is, stel de Manager **van de** Configuratie in werking om diverse modules van Vormen AEM te vormen en aangewezen configuraties te plaatsen. Samen met het vormen van montages, staat het toe om de weg van Globale Opslag van Gegevens (GDS) en crx-bewaarplaats te specificeren.

      >[!NOTE] Selecteer in het scherm Taakselectie bijwerken de optie **[!UICONTROL Upgrade uitvoeren in Adobe Experience Manager Forms 6.2.0]** . Met de optie **[!UICONTROL Upgrade uitvoeren vanuit Adobe Experience Manager Forms 6.2.0]** kan configuratiebeheer een upgrade uitvoeren van LiveCycle ES3 naar AEM 6.4 Forms.

   1. (Niet vereist voor de beveiligingsmodule van AEM Forms-documenten) Voer een upgrade uit en importeer de CRX-opslagruimte naar de AEM 6.4 Forms-server.

      >[!NOTE] Nadat de crx-gegevensopslagruimte is bijgewerkt en de inhoud is gemigreerd, wijzigt u het wachtwoord van de beheerdersaccount. Zie Het wachtwoord [wijzigen voor een bestaande gebruiker](/help/sites-administering/granite-user-group-admin.md)voor gedetailleerde instructies.
1. Voer de post-plaatsingstaken uit om login geloofsbrieven te verifiëren, documentdiensten, correspondentiebeheer, documentveiligheid, en meer afhankelijk van uw gebruiksgeval te vormen.
1. Controleer of de upgrade van de server is geslaagd:

   Voer een aantal routinebewerkingen uit op de geüpgrade AEM Forms-server om ervoor te zorgen dat de server correct is bijgewerkt. U kunt enkele gemigreerde formulieren invullen en verzenden of documenten beveiligen voor een geslaagde upgrade.

   >[!NOTE] In AEM 6.4 Forms is de structuur van crx-gegevensopslagruimte gewijzigd. Nadat u een upgrade naar AEM 6.4-formulieren hebt uitgevoerd, gebruikt u de gewijzigde paden voor aanpassing die u opnieuw maakt. Zie [Forms Repository Reform in AEM 6.4 voor een volledige lijst met gewijzigde paden](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md).

**Afhankelijk van uw bestaande omgeving en toepassingsserver kiest u een van de volgende documenten en volgt u de gedetailleerde instructies:**

* [Upgrade van LiveCycle ES3 naar AEM 6.4-formulieren voor JBoss](assets/upgrade-jboss-livecycle-es3.pdf)
* [Upgrade van LiveCycle ES3 naar AEM 6.4 Forms for WebLogic](assets/upgrade-weblogic-livecycle-es3.pdf)
* [Upgrade van LiveCycle ES3 naar AEM 6.4 Forms for WebSphere](assets/upgrade-websphere-livecycle-es3.pdf)
* [Upgrade van LiveCycle ES3 naar AEM 6.4-formulieren met JBoss Turnkey](assets/upgrade-turnkey-livecycle-es3.pdf)
