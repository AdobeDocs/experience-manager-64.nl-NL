---
title: AEM Forms over OSGi-groepen en -voorrechten
seo-title: AEM Forms on OSGi Groups and Privileges
description: Wijs gebruikers aan de groepen toe om AEM Forms op OSGi te beheren
seo-description: Assign users to the groups to manage AEM Forms on OSGi
uuid: 9ebb3a4e-4c0e-4105-921f-58077fc45281
contentOwner: anujkapo
products: SG_EXPERIENCEMANAGER/6.4/FORMS
content-type: reference
topic-tags: Configuration
discoiquuid: 71412f5d-ff34-415f-baf8-d300756b93a9
role: Admin
exl-id: a79e863e-c316-422e-a565-b0ffdeffcc00
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---

# AEM Forms over OSGi-groepen en -voorrechten {#aem-forms-on-osgi-groups-and-privileges}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Wijs gebruikers aan de groepen toe om AEM Forms op OSGi te beheren

U kunt [groepen maken](/help/sites-administering/user-group-ac-admin.md#group-administration) en beleid en [gebruikers](/help/sites-administering/user-group-ac-admin.md#user-administration) aan de groepen in AEM. Dit beleid controleert voorrechten van de gebruikers die deel van de groep uitmaken.

Zodra u installeert [AEM Forms-invoegtoepassing](/help/forms/using/installing-configuring-aem-forms-osgi.md), zijn de in dit artikel vermelde groepen, zoals gebruiker van formulieren en gebruiker van formulieren, automatisch beschikbaar voor toewijzing. De volgende lijst maakt een lijst van de taken een gebruiker voor AEM Forms op OSGi kan uitvoeren die op de groepstoewijzingen wordt gebaseerd:

<table> 
 <tbody>
  <tr>
   <td>Groep</td> 
   <td>Taken</td> 
  </tr>
  <tr>
   <td>formuliergebruiker <sup>[1]</sup></td> 
   <td>
    <ul> 
     <li>Aangepaste formulieren maken, voorvertonen, publiceren en verzenden</li> 
     <li>Interactieve communicatie en documentfragmenten maken, voorvertonen en publiceren</li> 
     <li>Elementen uploaden naar een AEM-instantie</li> 
     <li>Thema's maken</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>formulieren-grootgebruikers</td> 
   <td>
    <ul> 
     <li>Aangepaste formulieren maken, voorvertonen, publiceren en verzenden</li> 
     <li>Interactieve communicatie en documentfragmenten maken, voorvertonen en publiceren</li> 
     <li>Scripts maken voor adaptieve formulieren met behulp van code-editor</li> 
     <li>Elementen uploaden, inclusief scripts</li> 
     <li>Thema's maken</li> 
     <li>Pakketten importeren die XDP bevatten</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>formulierverzendingsrevisoren</td> 
   <td>
    <ul> 
     <li>Herziening</li> 
     <li>Indieningen goedkeuren of afwijzen</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>sjabloonauteurs <sup>[2]</sup></td> 
   <td>
    <ul> 
     <li>Aangepaste formulieren of interactieve communicatiesjablonen maken en hiervan een voorbeeld bekijken</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td><p>fdm-auteurs</p> </td> 
   <td>
    <ul> 
     <li>Een formuliergegevensmodel maken en wijzigen</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>cm-user-agent</td> 
   <td>
    <ul> 
     <li>Toegang tot correspondentiebeheerbrieven of interactieve communicatie met de gebruikersinterface van de Agent</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td><p>workfloweditors</p> </td> 
   <td>
    <ul> 
     <li>Een inbox-toepassing maken</li> 
     <li>Een workflowmodel maken</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>workflowgebruiker</td> 
   <td>
    <ul> 
     <li>AEM inbox-toepassingen gebruiken</li> 
     <li>Workflowinstanties beheren</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>fd-beheerders</td> 
   <td>
    <ul> 
     <li>PDF Generator configureren</li> 
     <li>Gecontroleerde map configureren</li> 
     <li>Workflowtoepassingen beheren</li> 
    </ul> </td> 
  </tr>
 </tbody>
</table>

1. De gebruiker met de rechten van een gebruikersgroep voor formulieren kan geen scripts schrijven voor adaptieve formulieren.
1. De gebruiker met de groepsrechten voor sjabloonauteurs kan geen scripts voor sjablonen schrijven.
