---
title: Upgrade naar AEM 6.4 Forms
seo-title: Upgrade to AEM 6.4 Forms
description: U kunt een directe verbetering van AEM 6.1 Forms, AEM 6.2 Forms, en LiveCycle ES4 SP1 aan AEM 6.3 Forms uitvoeren.
seo-description: You can perform a direct upgrade from AEM 6.1 Forms, AEM 6.2 Forms, and LiveCycle ES4 SP1 to AEM 6.3 Forms.
uuid: 1435246a-9215-4d88-b52c-59a5c329bb77
content-type: reference
products: SG_EXPERIENCEMANAGER/6.3/FORMS
topic-tags: installing
geptopics: SG_AEMFORMS/categories/jee
discoiquuid: e745033f-8015-4fae-9d82-99d35802c0a6
role: Admin
exl-id: 183ed9c6-6a9a-4932-8405-5ae2c6fac1ec
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 0%

---

# Upgrade naar AEM 6.4 Forms op OSGi {#upgrade-to-aem-forms-osgi}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Gebruik een van de volgende upgradepaden, al naar gelang uw omgeving.

## AEM 6.2 Forms of AEM 6.3 Forms > AEM 6.4 Forms {#upgrade-aem-forms-62-63-to-64}

U kunt een directe upgrade uitvoeren van AEM 6.2 Forms of AEM 6.3 Forms naar AEM 6.4 Forms. Ga als volgt te werk:

1. Upgrade de bestaande AEM naar AEM 6.4. De stappen worden hieronder weergegeven:

   1. Installeer het nieuwste servicepakket en de nieuwste patches voor AEM 6.2 Forms of AEM 6.3 Forms. Zie voor meer informatie:

      * [Opmerkingen bij de release AEM 6.2](https://helpx.adobe.com/experience-manager/6-2/release-notes.html)
      * [Opmerkingen bij de release AEM 6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes.html)
      * [AEM Sustenance Hub](https://helpx.adobe.com/experience-manager/aem-releases-updates.html)
   1. Bereid de broninstantie voor de verbetering voor. Voor gedetailleerde stappen raadpleegt u [Upgrade naar AEM 6.4](/help/sites-deploying/upgrade.md#preparing%20the%20source%20instance).
   1. Download de [AEM 6.4 QuickStart](/help/sites-deploying/deploy.md#getting%20the%20software).
   1. **(Alleen Unix/Linux-gebaseerde installaties)** Als u UNIX of Linux als onderliggend besturingssysteem gebruikt, opent u het terminalvenster, navigeert u naar de map met crx-quickstart en voert u de volgende opdracht uit:

      `chmod -R 755 ../crx-quickstart`

   1. Voer een upgrade uit van uw AEM naar AEM 6.3. Voor instructies die stap voor stap worden uitgevoerd, raadpleegt u [Upgrade naar AEM 6.4](/help/sites-deploying/upgrade.md).

      Voordat u verdergaat met de volgende stappen, wacht u tot de berichten ServiceEvent REGISTERED en ServiceEvent UNREGISTERED niet meer worden weergegeven in het dialoogvenster &lt;crx-repository>/error.log.

      >[!NOTE]
      >
      >Nadat de server is gestart, blijven enkele AEM Forms-bundels in de installatiestatus staan. Het aantal bundels kan voor elke installatie variëren. U kunt de status van deze bundels veilig negeren. De bundels worden weergegeven op `https://[server]:[port]/system/console/`.


1. Installeer het AEM Forms-invoegtoepassingspakket. De stappen worden hieronder weergegeven:

   1. Openen [Softwaredistributie](https://experience.adobe.com/downloads). U hebt een Adobe ID nodig om u aan te melden bij de softwaredistributie.
   1. Tikken **[!UICONTROL Adobe Experience Manager]** beschikbaar in het koptekstmenu.
   1. In de **[!UICONTROL Filters]** sectie:
      1. Selecteren **[!UICONTROL Forms]** van de **[!UICONTROL Solution]** vervolgkeuzelijst.
      1. Selecteer de versie en typ voor het pakket. U kunt ook de opdracht **[!UICONTROL Search Downloads]** om de resultaten te filteren.
   1. Tik op de pakketnaam die van toepassing is op het besturingssysteem. Selecteer **[!UICONTROL Accept EULA Terms]** en tikken **[!UICONTROL Download]**.
   1. Openen [Pakketbeheer](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html)  en klik op **[!UICONTROL Upload Package]** om het pakket te uploaden.
   1. Selecteer het pakket en klik op **[!UICONTROL Install]**.

      U kunt het pakket ook downloaden via de directe koppeling die wordt vermeld in [AEM Forms-releases](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) artikel.

      >[!NOTE]
      >
      >Nadat het pakket is geïnstalleerd, wordt u gevraagd om de AEM opnieuw te starten. **Stop niet onmiddellijk de server.** Voordat u de AEM Forms-server stopt, wacht u tot de berichten ServiceEvent REGISTERED en ServiceEvent UNREGISTERED niet meer worden weergegeven in de &lt;crx-repository>Het bestand /error.log en het logbestand zijn stabiel. Houd er rekening mee dat een aantal pakketten in de installatiestatus kunnen blijven staan. U kunt de status van deze verpakkingen veilig negeren.

   1. Stop de AEM instantie en verwijder de volgende bestanden:

      * `[AEM_Installation_Directory]\[crx-quickstart]\launchpad\ext\bcmail-jdk15-1.35`
      * `[AEM_Installation_Directory]\[crx-quickstart]\launchpad\ext\bcprov-jdk15-1.35`
   1. Start de AEM.


1. Voer activiteiten na de installatie uit.

   * **Migratiehulpprogramma uitvoeren**

      Het migratiehulpprogramma maakt de adaptieve formulieren en het beheer van correspondentie van eerdere versies compatibel met AEM 6.4-formulieren. U kunt het hulpprogramma downloaden van AEM softwaredistributie. Voor geleidelijke informatie om het migratienut te vormen en te gebruiken, zie [migratiehulpprogramma](/help/forms/using/migration-utility.md).

      Als u [Voorbeeld voor het integreren van concepten en verzendingscomponenten](integrate-draft-submission-database.md) met de database en upgrade vanaf een vorige versie, voert u de volgende SQL-query&#39;s uit nadat u de upgrade hebt uitgevoerd:

      ```
      UPDATE metadata m, additionalmetadatatable am
      SET m.dataType = am.value
      WHERE m.id = am.id
      AND am.key = 'dataType'
      ```

      ```
      DELETE from additionalmetadatatable
      WHERE `key` = 'dataType'
      ```

   * **(Als u alleen een upgrade uitvoert van AEM 6.2 Forms of eerdere versies, dient u Acrobat Sign opnieuw te configureren**

      Als u Acrobat Sign in de vorige versie van AEM Forms had geconfigureerd, configureert u Acrobat Sign opnieuw vanaf AEM Cloud-services. Zie voor meer informatie [Acrobat Sign integreren met AEM Forms](/help/forms/using/adobe-sign-integration-adaptive-forms.md).

   * **(Als u een upgrade uitvoert van alleen AEM 6.2 Forms of eerdere versies) Analyses en rapporten opnieuw samenstellen**

      In AEM 6.4 Forms, zijn de verkeersvariabele voor bron en succesgebeurtenis voor indruk niet beschikbaar. Als u dus een upgrade uitvoert van AEM 6.2 Forms of eerdere versies, stopt AEM Forms met het verzenden van gegevens naar de Adobe Analytics-server en zijn er geen analyserapporten voor adaptieve formulieren beschikbaar. Bovendien introduceert AEM 6.4 Forms verkeersvariabele voor de versie van formulieranalyse en succesgebeurtenis voor de hoeveelheid tijd die aan een veld wordt doorgebracht. Configureer daarom analyses en rapporten voor uw AEM Forms-omgeving. Voor gedetailleerde stappen raadpleegt u [Analyses en rapporten configureren](/help/forms/using/configure-analytics-forms-documents.md).

1. Controleer of de upgrade van de server is geslaagd, of alle gegevens zijn gemigreerd en of deze op de normale manier kunnen werken.

   * **Controleer de status van de bundels:** Zorg ervoor dat alle bundels actief zijn.
   * **Verifieer replicatie en omgekeerde replicatie:** Een aantal gemigreerde formulieren publiceren, invullen en verzenden. Controleer ook de verzonden gegevens.
   * **Toegang tot gebruikersinterfaces voor beheer en ontwikkelaar verifiëren:** Meld u aan bij AEM instantie van een beheerdersaccount en controleer of u toegang hebt tot de volgende URL&#39;s:

      * `https://[server]:[port]/crx/packmgr`
      * `https://[server]:[port]/crx/de`
      * `https://[server]:[port]/aem/forms.html/content/dam/formsanddocuments`

   >[!NOTE]
   In AEM 6.4 Forms is de structuur van crx-repository veranderd. Nadat u een upgrade hebt uitgevoerd naar AEM 6.4-formulieren, gebruikt u de gewijzigde paden voor aanpassing die u opnieuw maakt. Voor de volledige lijst met gewijzigde paden raadpleegt u [Forms Repositoregeling Herstructurering in AEM 6.4](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md).

## AEM 6.0 Forms en AEM 6.1 Forms > AEM 6.4 Forms {#upgrade-aem-forms-60-61-to-64}

Direct upgradepad van **AEM 6.0 Forms** en **AEM 6.1 Forms** tot AEM 6.4 Forms is niet beschikbaar. Een tussenpersoon uitvoeren [upgrade naar AEM 6.2 Forms](/help/forms/using/upgrade.md) of [upgrade naar AEM 6.3 Forms](/help/forms/using/upgrade.md) en upgrade vervolgens van AEM 6.2 Forms of AEM 6.3 Forms naar AEM 6.4 Forms.
