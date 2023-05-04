---
title: Taken in een organisatiehiërarchie beheren met de beheerweergave
seo-title: Managing tasks in an organizational hierarchy using Manager View
description: Hoe managers en organisatiehoofden toegang hebben tot de taken van hun directe en indirecte rapporten en deze kunnen bewerken op het tabblad Te doen in de AEM Forms-werkruimte.
seo-description: How managers and organization heads can access and work on the tasks of their direct and indirect reports in the To-do tab in AEM Forms workspace.
uuid: a44d5a64-c03a-4337-8577-b121e6202449
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: c7cf28bf-2806-47bc-a803-8bc0e803fc4d
exl-id: 28877528-2f91-4ee0-b9d8-c7df364ed803
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 0%

---

# Taken in een organisatiehiërarchie beheren met de beheerweergave {#managing-tasks-in-an-organizational-hierarchy-using-manager-view}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

In de werkruimte van AEM Forms, kunnen de managers tot de taken nu toegang hebben die aan iedereen in hun hiërarchie worden toegewezen - directe of indirecte rapporten - en diverse acties op hen uitvoeren. De taken zijn beschikbaar op het tabblad Te doen in de AEM Forms-werkruimte. De acties die op de taken van directe rapporten worden gesteund zijn:

**Doorsturen** Een taak door:sturen van direct rapport aan om het even welke gebruiker.

**Claim** Vorderen van een taak van een rechtstreeks verslag.

**Claim &amp; Openen** Vordeer een taak van een direct rapport en open het automatisch in de te doen lijst van de manager.

**Afwijzen** Weiger een taak die aan een direct rapport door één of andere andere gebruiker wordt doorgestuurd. Deze optie is beschikbaar voor de taken die door andere gebruikers aan een direct rapport door:sturen.

AEM Forms beperkt de toegang van gebruikers tot slechts die taken waarvoor de gebruiker toegangsbeheer (ACL) heeft. Een dergelijke controle zorgt ervoor dat een gebruiker alleen de taken kan ophalen waarop de gebruiker toegangsmachtigingen heeft. Met behulp van externe webservices en implementaties om de hiërarchie te definiëren, kan een organisatie de definitie van manager en directe rapporten aanpassen aan hun behoeften.

1. Maak een DSC. Voor meer informatie, zie het onderwerp van &quot;het Ontwikkelen van Componenten voor Vormen AEM&quot;in [Programmeren met AEM Forms](https://www.adobe.com/go/learn_aemforms_programming_63) hulplijn.
1. In DSC, bepaal nieuw SPI voor hiërarchiebeheer om directe rapporten en hiërarchie binnen de gebruikers van AEM Forms te bepalen. Hier volgt een voorbeeld van een Java™-codefragment.

   ```as3
   public class MyHierarchyMgmtService 
   { 
        /*
       Input : Principal Oid for a livecycle user
       Output : Returns true when the user is either the service invoker OR his direct/indirect report.
       */
       boolean isInHierarchy(String principalOid) {
   
       }
   
       /* 
       Input : Principal Oid for a livecycle user
       Output : List of principal Oids for direct reports of the livecycle user
       A user may get direct reports only for himself OR his direct/indirect reports.
       So the API is functionally equivalent to - 
       isInHierarchy(principalOid) ? <return direct reports> : <return empty list>
       */
       List<String> getDirectReports(String principalOid) {
   
       }
   
       /* 
       Returns whether a livecycle user has direct reports or not.
       It's functionally equivalent to -
       getDirectReports(principalOid).size()>0
       */
       boolean isManager(String principalOid) {
   
       }  
   }
   ```

1. Maak een bestand component.xml. Zorg ervoor dat de specificatie-id gelijk is aan de code die hieronder wordt weergegeven. Hieronder volgt een voorbeeldcodefragment dat u opnieuw kunt gebruiken.

   ```as3
   <component xmlns="https://adobe.com/idp/dsc/component/document"> 
       <component-id>com.adobe.sample.SampleDSC</component-id> 
       <version>1.1</version> 
       <supports-export>false</supports-export> 
         <descriptor-class>com.adobe.idp.dsc.component.impl.DefaultPOJODescriptorImpl</descriptor-class> 
         <services> 
           <service name="MyHierarchyMgmtService" title="My hierarchy management service" orchestrateable="false"> 
           <auto-deploy service-id="MyHierarchyMgmtService" category-id="Sample DSC" major-version="1" minor-version="0" /> 
           <description>Service for resolving hierarchy management.</description> 
            <specifications> 
            <specification spec-id="com.adobe.idp.taskmanager.dsc.enterprise.HierarchyManagementProvider"/> 
            </specifications> 
           <specification-version>1.0</specification-version> 
           <implementation-class>com.adobe.sample.hierarchymanagement.MyHierarchyMgmtService</implementation-class> 
           <request-processing-strategy>single_instance</request-processing-strategy> 
           <supported-connectors>default</supported-connectors> 
           <operation-config> 
               <operation-name>*</operation-name> 
               <transaction-type>Container</transaction-type> 
               <transaction-propagation>supports</transaction-propagation> 
               <!--transaction-timeout>3000</transaction-timeout--> 
           </operation-config> 
           <operations> 
               <operation anonymous-access="true" name="isInHierarchy" method="isInHierarchy"> 
                   <input-parameter name="principalOid" type="java.lang.String" /> 
                   <output-parameter name="result" type="java.lang.Boolean"/> 
               </operation> 
               <operation anonymous-access="true" name="getDirectReports" method="getDirectReports"> 
                   <input-parameter name="principalOid" type="java.lang.String" /> 
                   <output-parameter name="result" type="java.util.List"/> 
               </operation> 
               <operation anonymous-access="true" name="isManager" method="isManager"> 
                   <input-parameter name="principalOid" type="java.lang.String" /> 
                   <output-parameter name="result" type="java.lang.Boolean"/> 
               </operation> 
               </operations> 
               </service> 
         </services>
   </component>
   ```

1. Implementeer DSC via Workbench. Opnieuw starten `ProcessManagementTeamTasksService` service.
1. Mogelijk moet u de browser vernieuwen of u opnieuw afmelden/aanmelden bij de gebruiker.

Het volgende scherm illustreert de toegang tot van de taken van directe rapporten en de beschikbare acties.

![cu_manager_view](assets/cu_manager_view.png)

De taken van de toegang tot directe rapporten en handelen op de taken
