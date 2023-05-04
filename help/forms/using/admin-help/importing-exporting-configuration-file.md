---
title: Het configuratiebestand importeren en exporteren
seo-title: Importing and exporting the configuration file
description: Leer hoe u het configuratiebestand importeert en exporteert om servervoorkeuren te bewerken of een ander exemplaar van een AEM formulierproduct te configureren.
seo-description: Learn how to import and export the configuration file in order to edit server preferences or configure another AEM forms product instance.
uuid: 32e8a709-2d7c-4740-9533-d53aa751bc58
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_user_management
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: c1636537-f7dc-48d8-a3f0-9052bcd28b62
exl-id: dbad776a-60fd-4fcc-ba2a-a2f379f5462c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---

# Het configuratiebestand importeren en exporteren {#importing-and-exporting-the-configuration-file}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Gebruik de pagina Handmatige configuratie om een kopie van de configuratie-instellingen in XML-indeling te downloaden. De instellingen in dit bestand bepalen alle servervoorkeuren. U kunt het bestand vervolgens bewerken en opnieuw naar de server uploaden. U kunt het bestand ook gebruiken om een ander exemplaar van een AEM formulierproduct te configureren.

Om veiligheidsrisico&#39;s te vermijden, bindt wachtwoordwaarde voor de folderserver niet inbegrepen in een uitgevoerd configuratiedossier. Werk het wachtwoord in het XML-bestand bij voordat u het bestand naar een nieuw systeem importeert.

>[!NOTE]
>
>Wanneer u het configuratiebestand importeert, worden AEM formulieren opnieuw geconfigureerd op basis van de informatie in het bestand. Alleen een systeembeheerder of een consultant voor professionele services die bekend is met het AEM formulierproduct en XML, kan overwegen het configuratiebestand te wijzigen. Zij kunnen het configuratiedossier, bijvoorbeeld, moeten uitgeven om een bedorven het plaatsen opnieuw te vormen.

**De configuratiegegevens exporteren**

1. Klik in Beheerconsole op Instellingen > Gebruikersbeheer > Configuratie > Configuratiebestanden importeren en exporteren.
1. Klik op Exporteren. Als u Microsoft Internet Explorer gebruikt, wordt u gevraagd een locatie op te geven om het bestand op te slaan. Als u Firefox gebruikt, wordt het bestand opgeslagen op uw bureaublad.

**De configuratiegegevens importeren**

1. Klik in Beheerconsole op Instellingen > Gebruikersbeheer > Configuratie > Configuratiebestanden importeren en exporteren.
1. Klik doorbladeren om het configuratiedossier te vinden, de Invoer te klikken, en dan O.K. te klikken.
