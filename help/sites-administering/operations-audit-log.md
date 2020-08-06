---
title: Onderhoud controlelogbestand in AEM 6
seo-title: Onderhoud controlelogbestand in AEM 6
description: Meer informatie over onderhoud van controlelogbestanden in AEM.
seo-description: Meer informatie over onderhoud van controlelogbestanden in AEM.
uuid: 212de4df-6bf4-434c-94e1-74186d21945a
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 565d89de-b3ca-41a5-8e1c-d10905c25fb5
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 0%

---


# Onderhoud controlelogbestand in AEM 6{#audit-log-maintenance-in-aem}

AEM gebeurtenissen die in aanmerking komen voor accountlogboekregistratie, genereren veel gearchiveerde gegevens. Deze gegevens kunnen na verloop van tijd snel groeien als gevolg van replicaties, het uploaden van bedrijfsmiddelen en andere systeemactiviteiten.

Het onderhoud van het controlelogboek omvat verscheidene delen van functionaliteit die de capaciteit toelaat om het onderhoud van het controlelogboek onder specifiek beleid te automatiseren.

Het wordt uitgevoerd als configureerbare wekelijkse onderhoudstaak en is toegankelijk via de de monitorconsole van het Dashboard van Verrichtingen.

Raadpleeg voor meer informatie de documentatie bij het Dashboard [voor bewerkingen](/help/sites-administering/operations-dashboard.md).

Er zijn drie typen opties voor het opschonen van controlelogbestanden:

1. [Pagina-auditlogboek leegmaken](/help/sites-administering/operations-audit-log.md#configure-page-audit-log-purging)
1. [DAM-controlelogbestand leegmaken](/help/sites-administering/operations-audit-log.md#configure-dam-audit-log-purging)
1. [Controlelogboek replicatie](/help/sites-administering/operations-audit-log.md#configure-replication-audit-log-purging)

Elk kan worden gevormd door regels in de Console van het AEM te creëren. Nadat zij zijn gevormd, kunt u hen teweegbrengen door naar **Hulpmiddelen - Verrichtingen - Onderhoud - het Venster** van het Weekonderhoud te gaan en de Taak **van het Onderhoud** AuditLog in werking te stellen.

## Logbestand voor controle van pagina configureren {#configure-page-audit-log-purging}

Voer de volgende stappen uit om het opschonen van controlelogbestanden te configureren:

1. Ga naar de webconsolebeheerder door uw browser naar `http://localhost:4502/system/console/configMgr/`

1. Zoek naar een punt genoemd de regel **van de Schrapping van het Logboek van de controle van** Pagina&#39;s en klik het.

   ![chlimage_1-365](assets/chlimage_1-365.png)

1. Vervolgens configureert u de zuiveringsplanner volgens uw vereisten. De beschikbare opties zijn:

   * **Naam regel:** de naam van de regel inzake controlebeleid;
   * **Inhoudspad:** het pad van de inhoud waarop de regel van toepassing is;
   * **Minimumleeftijd:** de tijd in dagen waarop de auditlogs moeten worden bewaard;
   * **Type controlelogboek:** het type controlelogboek dat moet worden gezuiverd.

   >[!NOTE]
   >
   >Het inhoudspad is alleen van toepassing op onderliggende knooppunten van het `/var/audit/com.day.cq.wcm.core.page` knooppunt in de opslagplaats.

1. Sla de regel op.
1. De regel u enkel creeerde moet in het Dashboard van Verrichtingen worden blootgesteld opdat het wordt uitgevoerd. Om dit te doen, ga **Hulpmiddelen - Verrichtingen - Onderhoud** van het AEM Welkome scherm.

1. Druk op de **Wekelijkse onderhoudsievenster** .

1. U zult de onderhoudstaak vinden die reeds onder de **AuditLog van de Taak** kaart van het Onderhoud aanwezig is.

   ![chlimage_1-366](assets/chlimage_1-366.png)

1. U kunt of de datum van de volgende uitvoering inspecteren, het vormen, of het manueel uitvoeren door de spelknoop te drukken.

In AEM 6.3, als het geplande onderhoudsvenster sluit alvorens de taak van het Logboek van de Controle kan voltooien, houdt de taak automatisch op. Het wordt hervat wanneer het volgende onderhoudsvenster wordt geopend.

**Met AEM 6.4** kunt u een lopende Taak van de Wrijving van het Logboek van de Controle manueel tegenhouden door het pictogram van het **Einde** te klikken. Bij de volgende uitvoering wordt de taak veilig hervat.

>[!NOTE]
>
>Om een einde te maken aan de onderhoudstaak, moet de uitvoering worden opgeschort zonder dat het spoor van de reeds in uitvoering zijnde baan verloren gaat.

## DAM-controlelogbestand opschonen {#configure-dam-audit-log-purging}

1. Ga naar de systeemconsole op *https://&lt;serveradres>:&lt;serverport>/system/console/configMgr*
1. Zoek naar **DAM de regel van de Zuivering** van het controlelogboek en klik het resultaat.
1. In het volgende venster, vorm dienovereenkomstig uw regel. De opties zijn:

   * **Naam regel:** de naam van de regel inzake controlebeleid;
   * **Inhoudspad:** het pad van de inhoud waarop de regel van toepassing is
   * **Minimumleeftijd:** de tijd in dagen dat de auditlogs moeten worden bewaard
   * **Typen auditlogbestandgebeurtenissen:** de typen DAM-auditgebeurtenissen die moeten worden gewist.

1. Klik op **Opslaan** om uw configuratie op te slaan

## Logboek voor replicatiecontrole configureren  {#configure-replication-audit-log-purging}

1. Ga naar de systeemconsole op *https://&lt;serveradres>:&lt;serverport>/system/console/configMgr*
1. Zoeken naar **Replication audit Log Purge Scheduler** en klik op het resultaat
1. In het volgende venster, vorm dienovereenkomstig uw regel. De opties zijn:

   * **Naam regel:** de naam van de regel van het controlebeleid
   * **Inhoudspad:** het pad van de inhoud waarop de regel van toepassing is
   * **Minimumleeftijd:** de tijd in dagen dat de auditlogs moeten worden bewaard
   * **Gebeurtenistypen van het Logboek van de controle:** de soorten de controlegebeurtenissen van de Replicatie die zouden moeten worden gezuiverd

1. Klik op **Opslaan** om de configuratie op te slaan.

