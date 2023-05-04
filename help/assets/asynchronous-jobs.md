---
title: asynchrone bewerkingen configureren in [!DNL Adobe Experience Manager].
description: U kunt asynchroon een aantal bronintensieve taken uitvoeren om de prestaties te optimaliseren in [!DNL Experience Manager Assets].
contentOwner: AG
feature: Asset Management
role: User
exl-id: 0abdfe87-d932-41dd-b1e6-9f5fa5b924fe
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 21%

---

# Asynchrone bewerkingen {#asynchronous-operations}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Om negatieve gevolgen voor de prestaties te verminderen, [!DNL Adobe Experience Manger Assets] verwerkt asynchroon bepaalde langlopende en hulpbronnenintensieve elementbewerkingen. Asynchrone verwerking omvat het navragen van veelvoudige taken en uiteindelijk het uitvoeren van hen op een periodieke manier afhankelijk van de beschikbaarheid van systeemmiddelen. Deze bewerkingen omvatten:

* Veel assets verwijderen.
* Veel assets verplaatsen, of assets met veel verwijzingen verplaatsen.
* Metagegevens van elementen bulksgewijs exporteren en importeren.

U kunt de status van asynchrone taken weergeven via de **[!UICONTROL Async Job Status]** pagina.

>[!NOTE]
>
>Standaard worden de [!DNL Assets] taken worden parallel uitgevoerd. Indien `N` het aantal CPU-cores is, `N/2` taken kunnen standaard parallel worden uitgevoerd. Als u aangepaste instellingen voor de taakwachtrij wilt gebruiken, wijzigt u de optie **[!UICONTROL Async Operation Default Queue]** van de [!UICONTROL Web Console]. Voor meer informatie raadpleegt u [wachtrijconfiguraties](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#queue-configurations).

## De status van asynchrone bewerkingen controleren {#monitoring-the-status-of-asynchronous-operations}

Wanneer [!DNL Assets] verwerkt een verrichting asynchroon, ontvangt u een bericht in uw [!DNL Experience Manager] [Inbox](/help/sites-authoring/inbox.md) en via e-mail. Navigeer naar de pagina **[!UICONTROL Async Job Status]** om de status van de asynchrone bewerkingen in detail weer te geven.

1. In de [!DNL Experience Manager] interface klikken **[!UICONTROL Operations]** > **[!UICONTROL Jobs]**.

1. Controleer op de pagina **[!UICONTROL Async Job Status]** de details van de bewerkingen.

   ![Status en details van asynchrone bewerkingen](assets/job_status.png)

   Om de voortgang van een operatie te controleren, raadpleegt u de **[!UICONTROL Status]** kolom. Afhankelijk van de voortgang wordt een van de volgende statussen weergegeven:

   * **[!UICONTROL Active]**: De bewerking wordt verwerkt.
   * **[!UICONTROL Success]**: De bewerking is voltooid.
   * **[!UICONTROL Fail]** of **[!UICONTROL Error]**: De bewerking kan niet worden verwerkt.
   * **[!UICONTROL Scheduled]**: De bewerking is gepland voor verwerking op een later tijdstip.

1. Als u een actieve bewerking wilt stoppen, selecteert u deze in de lijst en klikt u op **[!UICONTROL Stop]** ![stoppictogram](assets/do-not-localize/stop_icon.svg) op de werkbalk.

1. Als u meer details wilt weergeven, bijvoorbeeld beschrijving en logbestanden, selecteert u de bewerking en klikt u op **[!UICONTROL Open]** ![open_icon](assets/do-not-localize/edit_icon.svg) op de werkbalk. De pagina met taakdetails wordt weergegeven.

   ![Details van een importtaak voor metagegevens](assets/job_details.png)

1. Als u de bewerking uit de lijst wilt verwijderen, selecteert u **[!UICONTROL Delete]** op de werkbalk. Klik op **[!UICONTROL Download]** om de details naar een csv-bestand te downloaden.

   >[!NOTE]
   >
   >U kunt een taak niet verwijderen als de status actief is of in de wachtrij staat.

## Voltooide taken wissen {#purge-completed-tasks}

[!DNL Experience Manager Assets] Voert een zuiveringstaak elke dag bij 100 uren uit om voltooide asynchrone taken te schrappen die meer dan een dag oud zijn.

<!-- TBD: Find out from the engineering team and mention the time zone of this 1:00 am task.
-->

U kunt het programma voor de zuiveringstaak en de duur wijzigen waarvoor de details van voltooide taken worden behouden alvorens zij worden geschrapt. U kunt ook het maximale aantal voltooide taken configureren waarvoor de details op elk gewenst moment behouden blijven.

1. In de [!DNL Experience Manager] interface klikken **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Web Console]**.
1. Open de **[!UICONTROL Adobe CQ DAM Async Jobs Purge Scheduled]** taak.
1. Geef het drempelaantal dagen op waarna voltooide taken worden verwijderd en het maximumaantal taken waarvoor details in de geschiedenis worden bewaard. Sla de wijzigingen op.

   ![Configuratie om het zuiveren van asynchrone taken te plannen](assets/purge_job.png)

## Drempel configureren voor asynchrone verwijderingsbewerkingen {#configure-thresholds-for-asynchronous-delete-operations}

Als het aantal elementen of mappen dat moet worden verwijderd, de ingestelde drempelwaarde overschrijdt, wordt de verwijderbewerking asynchroon uitgevoerd.

1. In de [!DNL Experience Manager] interface klikken **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Web Console]**.
1. Van de [!UICONTROL Web Console], opent u de **[!UICONTROL Async Delete Operation Job Processing]** configuratie.
1. In de **[!UICONTROL Threshold number of assets]** geeft u de drempelnummers op om elementen, mappen of verwijzingen asynchroon te verwijderen. Sla de wijzigingen op.

   ![De drempellimiet instellen voor de taak om elementen te verwijderen](assets/delete_threshold.png)

## Drempel voor asynchrone verplaatsingsbewerkingen configureren {#configure-thresholds-for-asynchronous-move-operations}

Als het aantal te verplaatsen elementen, mappen of verwijzingen het ingestelde drempelnummer overschrijdt, wordt de verplaatsingsbewerking asynchroon uitgevoerd.

1. In de [!DNL Experience Manager] interface, klik **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Web Console]**.
1. Van de [!UICONTROL Web Console], opent u de **[!UICONTROL Async Move Operation Job Processing]** configuratie.
1. In de **[!UICONTROL Threshold number of assets/references]** geeft u de drempelnummers op voor het asynchroon verplaatsen van elementen, mappen of verwijzingen. Sla de wijzigingen op.

   ![De drempellimiet instellen voor de taak om elementen te verplaatsen](assets/move_threshold.png)

>[!MORELIKETHIS]
>
>* [E-mail configureren in Experience Manager](/help/sites-administering/notification.md).
>* [Importeer/exporteer metadata van assets bulksgewijs](/help/assets/metadata-import-export.md).

