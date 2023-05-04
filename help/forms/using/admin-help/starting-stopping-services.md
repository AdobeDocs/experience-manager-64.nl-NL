---
title: Starten en stoppen van services
seo-title: Starting and stopping services
description: Leer hoe u services die aan AEM Forms-modules en de toepassingsserver en -database zijn gekoppeld, kunt starten en stoppen.
seo-description: Learn how to start and stop services associated with AEM Forms modules and the application server and database.
uuid: 8c831cb2-4165-4118-8a09-764cec4e5e05
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/managing_services
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: b93060bd-c6e1-40d2-8acd-ccafb8ed56da
exl-id: 6e0607d6-171c-4119-95a1-373b30fb63c1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# Starten en stoppen van services {#starting-and-stopping-services}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Er zijn twee soorten diensten die deel van AEM vormen uitmaken:

* Services die de toepassingsserver en database voor AEM formulieren besturen.
* Diensten die AEM vormen modules controleren

## De diensten verbonden aan AEM vormmodules beginnen of tegenhouden {#start-or-stop-the-services-associated-with-aem-forms-modules}

AEM formuliermodules (bijvoorbeeld Forms, Rights Management, Output) werken als services. Het kan gebeuren dat u de services voor deze AEM formuliermodules moet stoppen of starten. U moet bijvoorbeeld een AEM formulierservice stoppen en opnieuw starten nadat u een instelling voor de service hebt gewijzigd.

1. In beheerconsole klikken **Services** > **Toepassingen en services** > **Servicebeheer**.
1. Voor de pagina van het Beheer van de Dienst, selecteer de controledoos naast de dienst om te stoppen of te beginnen en Einde of Begin te klikken.

## De diensten van het begin of van het einde voor de toepassingsserver en gegevensbestand {#start-or-stop-services-for-the-application-server-and-database}

Een volledige implementatie van AEM formulieren omvat een toepassingsserver en databaseservices:

* *`[application server]`* voor AEM
* *`[database]`* voor AEM

In Windows zijn deze services toegankelijk via de **Administratieve gereedschappen** > **Deelvenster Services**. Als u bijvoorbeeld AEM formulieren op JBoss hebt geïnstalleerd met de methode key turnkey, zijn de volgende services beschikbaar op uw systeem:

* JBoss voor Adobe Experience Manager-formulieren
* MySQL voor Adobe Experience Manager-formulieren

Start of stop deze services door deze te selecteren in de lijst in het deelvenster Services en vervolgens op de desbetreffende actieknop in het deelvenster te klikken.

Voer in UNIX® of Linux de volgende tekst in via een opdrachtregel, waarbij *`[service name]`* Dit is de naam van de service die u controleert:

```as3
     ps -A | grep [service name]
```
