---
title: Gedeelde wachtrijen configureren
seo-title: Configuring Shared Queues
description: Met gedeelde wachtrijen kunt u gebruikerswachtrijen op effectieve wijze configureren en beheren. Leer hoe te om gedeelde rijen te vormen.
seo-description: Shared Queues allow you to configure and manage user queues effectively. Learn how to configure shared queues.
uuid: 69ab611d-334b-40a5-bd2d-533d4cb25eda
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_forms_workflow
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: fc403a60-b635-4334-9bf8-2f3d2036b2f3
exl-id: 40890db3-240c-4021-967a-b6b3eb1d4b7c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# Gedeelde wachtrijen configureren{#configuring-shared-queues}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met gedeelde wachtrijen kunt u gebruikerswachtrijen op effectieve wijze configureren en beheren. Een gebruikersrij is eenvoudig alle taken die aan een gebruiker worden toegewezen, zie [Lijsten met taken](https://help.adobe.com/en_US/livecycle/11.0/WorkspaceHelp/WS92d06802c76abadb-2b6ab502126beb6ba2f-7ffc.2.html) voor meer informatie . U kunt gebruikersrijen toewijzen, ongedaan maken en opnieuw toewijzen, afhankelijk van uw organisatorische behoeften. U kunt Gedeelde wachtrijen op twee manieren beheren:

**Toegang tot een gebruiker beheren**

Met deze optie kunt u de toegang tot een geselecteerde gebruikerswachtrij beheren.

**Toegang beheren door een gebruiker**

Met deze optie kunt u gedeelde wachtrijen beheren die aan een geselecteerde gebruiker zijn toegewezen.

## Toegang tot een geselecteerde gebruikerswachtrij beheren {#managing-access-to-a-selected-user-queue}

Met de functie Toegang tot een gebruiker beheren kunt u de toegang tot een geselecteerde gebruikerswachtrij beheren. U kunt toegang tot een geselecteerde gebruikersrij aan andere gebruikers in uw organisatie verlenen of intrekken. Kara Bowman is bijvoorbeeld niet meer aan het werk. Met behulp van de functie Toegang tot een gebruiker beheren kan haar wachtrij worden gedeeld met Akira Tanaka en John Jacobs voor voltooiing. Op een later tijdstip, wanneer Kara Bowman naar het kantoor terugkeert, kunt u de toegang tot haar rij intrekken van Akira Tanaka en John Jacobs.

Zodra gedeeld, kunnen deze taken door de gebruiker, met toegang tot de rij worden voltooid, gebruikend Werkruimte.

>[!NOTE]
>
>De Flex-werkruimte is verouderd voor AEM formulierrelease.

### Toegang tot een geselecteerde gebruikerswachtrij configureren {#configuring-access-to-a-selected-user-queue}

1. Meld u met een beheerdersaccount aan bij de beheerconsole.
1. Selecteren **Services** > **formulierworkflow** > **Gedeelde wachtrij**.

1. Zoek en selecteer op het tabblad Toegang tot een gebruiker beheren de gebruiker wiens wachtrij u wilt delen. Op elk gewenst moment wordt in het rechterondervenster de lijst weergegeven met gebruikers die toegang hebben tot de geselecteerde gebruikerswachtrij.
1. Zoek en selecteer de gebruiker in het linkerondervenster. Klik op Delen.
1. Klik op Opslaan om te voltooien.

### Toegang tot een geselecteerde gebruikerswachtrij intrekken {#revoking-access-to-a-selected-user-queue}

1. Meld u met een beheerdersaccount aan bij de beheerconsole.
1. Selecteren **Services** > **formulierworkflow** > **Gedeelde wachtrij**.

1. Zoek en selecteer op het tabblad Toegang tot een gebruiker beheren de gebruiker wiens wachtrij u wilt beheren.
1. In het rechterbenedendeelvenster wordt de lijst weergegeven met gebruikers die toegang hebben tot de geselecteerde gebruikerswachtrij. Selecteer de gebruiker en klik op Intrekken.
1. Klik op Opslaan om te voltooien.

## Wachtrijen beheren die aan een gebruiker zijn toegewezen {#managing-queues-assigned-to-a-user}

Met de functionaliteit Toegang door een gebruiker beheren kunt u wachtrijen beheren die aan een geselecteerde gebruiker zijn toegewezen. U kunt toegang tot gebruikersrijen verlenen of intrekken aan een geselecteerde gebruiker individueel. U wilt bijvoorbeeld de gebruikersrijen voor Akira Tanaka en John Jacobs toewijzen aan Kara Bowman. Met behulp van de functie Toegang beheren door een gebruiker kunt u zoeken naar Kara Bowman en toegang verlenen tot taken die zijn toegewezen aan Akira Tanaka en John Jacobs. Later kunt u de toegang van Kara Bowman tot deze gebruikerswachtrijen intrekken.

Zodra toegewezen, kunnen deze taken door de gebruiker worden voltooid gebruikend Werkruimte.

>[!NOTE]
>
>De Flex-werkruimte is verouderd voor AEM formulierrelease.

### Toegang verlenen tot een geselecteerde gebruikerswachtrij {#granting-access-to-a-selected-user-queue}

1. Meld u met een beheerdersaccount aan bij de beheerconsole.
1. Selecteren **Services** > **formulierworkflow** > **Gedeelde wachtrij**.

1. Zoek en selecteer op het tabblad Toegang tot gebruiker beheren de gebruiker van wie u de wachtrij wilt delen. Op elk gewenst moment wordt in het rechterondervenster de lijst weergegeven met gebruikers die toegang hebben tot de geselecteerde gebruikerswachtrij.
1. Zoek en selecteer in het linkerondervenster gebruikerswachtrijen die u met de geselecteerde gebruiker wilt delen. Klik op Delen.
1. Klik op Opslaan om te voltooien.

### Toegang tot een geselecteerde gebruikerswachtrij intrekken {#revoking_access_to_a_selected_user_queue-1}

1. Meld u met een beheerdersaccount aan bij de beheerconsole.
1. Selecteren **Services** > **formulierworkflow** > **Gedeelde wachtrij**.

1. Zoek en selecteer op het tabblad Toegang beheren door gebruiker van wie u de wachtrij wilt beheren.
1. In het rechterbenedendeelvenster wordt de lijst weergegeven met gebruikerswachtrijen die aan de geselecteerde gebruiker zijn toegewezen. Selecteer de gebruikerswachtrij en klik op Intrekken.
1. Klik op Opslaan om te voltooien.
