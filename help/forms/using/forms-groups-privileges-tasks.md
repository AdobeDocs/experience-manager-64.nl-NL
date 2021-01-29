---
title: AEM Forms over OSGi-groepen en -voorrechten
seo-title: AEM Forms over OSGi-groepen en -voorrechten
description: Wijs gebruikers aan de groepen toe om AEM Forms op OSGi te beheren
seo-description: Wijs gebruikers aan de groepen toe om AEM Forms op OSGi te beheren
uuid: 9ebb3a4e-4c0e-4105-921f-58077fc45281
contentOwner: anujkapo
products: SG_EXPERIENCEMANAGER/6.4/FORMS
content-type: reference
topic-tags: Configuration
discoiquuid: 71412f5d-ff34-415f-baf8-d300756b93a9
translation-type: tm+mt
source-git-commit: f02fde7583da87d48bf72bf569762e9d604d25ce
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---


# AEM Forms inzake OSGi-groepen en -voorrechten {#aem-forms-on-osgi-groups-and-privileges}

Wijs gebruikers aan de groepen toe om AEM Forms op OSGi te beheren

U kunt [groepen maken](/help/sites-administering/user-group-ac-admin.md#group-administration) en beleid en [gebruikers](/help/sites-administering/user-group-ac-admin.md#user-administration) toewijzen aan de groepen in AEM. Dit beleid controleert voorrechten van de gebruikers die deel van de groep uitmaken.

Nadat u [AEM Forms-add-on-pakket](/help/forms/using/installing-configuring-aem-forms-osgi.md) hebt geïnstalleerd, zijn de groepen die in dit artikel worden vermeld, zoals de gebruiker van het formulier en de gebruiker van het formulierbesturingssysteem, automatisch beschikbaar voor toewijzing. De volgende lijst maakt een lijst van de taken een gebruiker voor AEM Forms op OSGi kan uitvoeren die op de groepstoewijzingen wordt gebaseerd:

<table> 
 <tbody>
  <tr>
   <td>Groeperen</td> 
   <td>Taken</td> 
  </tr>
  <tr>
   <td>form-user <sup>[1]</sup></td> 
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

