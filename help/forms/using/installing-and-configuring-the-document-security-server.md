---
title: De documentbeveiligingsserver installeren en configureren
seo-title: Installing and configuring the document security server
description: Met documentbeveiliging kunt u alle gegevens die u in een ondersteunde indeling hebt opgeslagen, veilig verspreiden. Alleen geautoriseerde gebruikers hebben toegang tot beveiligde documenten.
seo-description: Use document security to safely distribute any information that you have saved in a supported format. Only authorized users can access protected documents.
uuid: 04c67a84-01ad-45b7-a590-822b1c067d52
contentOwner: khsingh
discoiquuid: 600d13e7-6655-41c5-aab4-c8e9e2a8d14f
role: Admin
exl-id: 9ce5e89b-76c9-464d-9caf-26a387c698fa
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 0%

---

# De documentbeveiligingsserver installeren en configureren {#installing-and-configuring-the-document-security-server}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met documentbeveiliging kunt u alle gegevens die u in een ondersteunde indeling hebt opgeslagen, veilig verspreiden. Alleen geautoriseerde gebruikers hebben toegang tot beveiligde documenten.

Met de beveiliging van Adobe Experience Manager Forms-documenten kunt u ervoor zorgen dat alleen geautoriseerde gebruikers uw documenten kunnen gebruiken. Met documentbeveiliging kunt u veilig alle informatie verspreiden die u in een ondersteunde indeling hebt opgeslagen. Tot de ondersteunde bestandsindelingen behoren de bestanden Adobe Portable Document Format (PDF) en Microsoft Word, Excel en PowerPoint.

U kunt documenten beschermen door beleid te gebruiken. De vertrouwelijkheidsmontages u in een beleid specificeert bepalen hoe een ontvanger een document kan gebruiken waarop u het beleid toepast. U kunt bijvoorbeeld opgeven of ontvangers tekst kunnen afdrukken of kopiëren, tekst kunnen bewerken of handtekeningen en opmerkingen kunnen toevoegen aan beveiligde documenten.

Het beleid wordt opgeslagen op de server van de Veiligheid van het Document; u past het beleid op documenten toe door uw cliënttoepassing. Wanneer u een beleid op een document toepast, beschermen de vertrouwelijkheidsmontages die in het beleid worden gespecificeerd de informatie die het document bevat. U kunt het document dat met een beleid is beveiligd, verspreiden onder ontvangers die door het beleid zijn gemachtigd.

Documentbeveiliging biedt ook clients, viewers en indexeerders om documenten te beveiligen, beveiligde documenten weer te geven en beveiligde documenten te indexeren. Voor gedetailleerde informatie over documentbeveiliging raadpleegt u [over documentbeveiliging](/help/forms/using/admin-help/document-security.md).

## Implementatietopologie  {#deployment-topology}

De beveiligingsmogelijkheden voor documenten zijn alleen beschikbaar in AEM Forms op JEE. U hebt één instantie van AEM Forms op JEE nodig. Indien nodig kunt u ook een cluster of farm van AEM Forms-servers maken. De volgende topologie is indicatieve topologie om het vermogen van de documentveiligheid in werking te stellen. Voor gedetailleerde informatie over de topologie, zie [Architectuur en plaatsingstopologieën voor AEM Forms](aem-forms-architecture-deployment.md).

<!--fix above link-->

![](do-not-localize/document-security-server_topology.png)

In het volgende diagram ziet u de typische architectuur voor AEM Forms Document Security:

![](do-not-localize/document-security-typical-environment.png)

## AEM Forms installeren op JEE {#installing-aem-forms-on-jee}

Voer de volgende stappen uit om AEM Forms op JEE te installeren en te configureren:

1. Download de AEM 6.4 Forms op het JEE-installatieprogramma van de [Adobe Licensing Website (LWS)](https://licensing.adobe.com/). U hebt een geldig onderhouds- en ondersteuningscontract nodig om het installatieprogramma te downloaden.
1. Lees de [AEM Forms on JEE Supported Platforms Document](/help/forms/using/aem-forms-jee-supported-platforms.md) en zorgen dat de software, hardware, besturingssystemen, toepassingsserver, databases, JDK&#39;s en andere infrastructuren klaar zijn om AEM Forms op JEE te installeren.
1. (Alleen niet-kant-en-klare installaties) Lees de [Installatie van één AEM Forms-server voorbereiden](https://www.adobe.com/go/learn_aemforms_prepareInstallsingle_64) of [Installatie van AEM Forms-servercluster voorbereiden](https://www.adobe.com/go/learn_aemforms_prepareInstallcluster_64) en klaar voor uw omgeving om AEM Forms op JEE te installeren en te configureren.
1. Afhankelijk van uw omgeving en toepassingsserver kiest u een van de volgende documenten en volgt u de instructies om de installatie te voltooien

   * [AEM Forms installeren en implementeren op JEE met JBoss turnkey](https://www.adobe.com/go/learn_aemforms_installTurnkey_64)
   * [AEM Forms installeren en implementeren op JEE voor JBoss](https://www.adobe.com/go/learn_aemforms_installJBoss_64)
   * [AEM Forms installeren en implementeren op JEE for WebLogic](https://www.adobe.com/go/learn_aemforms_installWebLogic_64)
   * [AEM Forms installeren en implementeren op JEE for WebSphere](https://www.adobe.com/go/learn_aemforms_installWebSphere_64)
   * [AEM Forms configureren op JEE in JBoss-cluster](https://www.adobe.com/go/learn_aemforms_clusterJBoss_64)
   * [AEM Forms configureren op JEE op WebLogic-cluster](https://www.adobe.com/go/learn_aemforms_clusterWebLogic_64)
   * [AEM Forms configureren op JEE op WebSphere-cluster](https://www.adobe.com/go/learn_aemforms_clusterWebSphere_64)

   >[!NOTE]
   >
   >Selecteer de optie Documentbeveiliging in het selectiescherm Module van AEM Forms in JEE Configuration Manager. Voor de optie Documentbeveiliging hoeft u geen andere module te selecteren.

## Volgende stappen {#next-steps}

* [Client- en serveropties configureren](/help/forms/using/admin-help/configuring-client-server-options.md)
* [Beleid maken en beheren](/help/forms/using/admin-help/creating-policies.md)
* [Beleidssets maken en beheren](/help/forms/using/admin-help/creating-policy-sets.md)
