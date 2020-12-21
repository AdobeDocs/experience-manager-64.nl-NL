---
title: 'Metagegevens gebruiken in een e-mailmelding '
seo-title: 'Metagegevens gebruiken in een e-mailmelding '
description: Metagegevens gebruiken om informatie in te vullen in een e-mailmelding in een formulierwerkstroom
seo-description: Metagegevens gebruiken om informatie in te vullen in een e-mailmelding in een formulierwerkstroom
uuid: 17e018c9-6bf8-4042-bba9-4ebe449304ac
topic-tags: publish
discoiquuid: bdf13893-630a-43cd-aaeb-c7c16bf4f8a6
translation-type: tm+mt
source-git-commit: 0797eeae57ac5a9676c6d308eaf2aaffab999d18
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 0%

---


# Metagegevens gebruiken in een e-mailmelding {#use-metadata-in-an-email-notification}

Metagegevens gebruiken om informatie in te vullen in een e-mailmelding in een formulierwerkstroom

Met de stap Taak toewijzen kunt u taken maken en toewijzen aan een gebruiker of groep. Wanneer een taak aan een gebruiker of een groep wordt toegewezen, wordt een e-mailbericht verzonden naar de bepaalde gebruiker of naar elk lid van de bepaalde groep. Een typisch [e-mailbericht](/help/forms/using/use-custom-email-template-assign-task-step.md) bevat verbinding van de toegewezen taak en informatie met betrekking tot de taak.

U kunt metagegevens in een e-mailsjabloon gebruiken om gegevens in een e-mailbericht dynamisch in te vullen. De waarde van de titel, beschrijving, vervaldatum, prioriteit, workflow en laatste datum in het volgende e-mailbericht wordt bijvoorbeeld dynamisch geselecteerd tijdens de runtime (wanneer een e-mailmelding wordt gegenereerd).

![default-email-template](assets/default-email-template.png)

Metagegevens worden opgeslagen in sleutelwaardeparen. U kunt de sleutel in het e-mailmalplaatje specificeren en de sleutel wordt vervangen met een waarde bij runtime (wanneer een e-mailbericht wordt geproduceerd). In het onderstaande codevoorbeeld is &quot;$ {workitem_title} &quot; bijvoorbeeld een sleutel. Deze wordt tijdens de runtime vervangen door de waarde &quot;Loan-Request&quot;.

```xml
subject=Task Assigned - ${workitem_title}

message=<html><body>\n\
 <table>\n\
  <tbody>\n\
   <tr>\n\
    <td>\n\
      Sample Company\n\
    </td>\n\
   </tr>\n\
   <tr>\n\
    <td>\n\
     <pre style="font-size: 13px; font-family: Helvetica, Arial, sans-serif;  font-weight: normal; color: #323232;"> Hello ${workitem_assignee},\n\
 The following task has been assigned to you:</pre>\n\
    </td>\n\
   </tr>\n\
   <tr>\n\
    <td>\n\
     <table>\n\
      <tbody>\n\
       <tr style="border-bottom: solid 2px #FFFCF9;">\n\
        <td> TITLE</td>\n\
        <td>\n\
         <p>${workitem_title}</p>\n\
        </td>\n\
       </tr>\n\
                            <tr style="border-bottom: solid 2px #FFFCF9;">\n\
        <td> DESCRIPTION</td>\n\
        <td>\n\
         <p>${workitem_description}</p>\n\
        </td>\n\
       </tr>\n\
       <tr style="border-bottom: solid 2px #FFFCF9;">\n\
        <td> DUE DATE</td>\n\
        <td>\n\
         <p>${workitem_due_date}</p>\n\
        </td>\n\
       </tr>\n\
       <tr style="border-bottom: solid 2px #FFFCF9;">\n\
        <td> PRIORITY</td>\n\
        <td>\n\
         <p>${workitem_priority}</p>\n\
        </td>\n\
       </tr>\n\
       <tr>\n\
        <td> WORKFLOW</td>\n\
        <td>\n\
         <p>${workitem_workflow}</p>\n\
        </td>\n\
       </tr>\n\
      </tbody>\n\
     </table>\n\
    </td>\n\
   </tr>\n\
   <tr style = "text-align: center; vertical-align: middle;">\n\
    <td> \n\
     <a href="${workitem_url}" target="_blank" style="background-color: #1EBBBB; font-size: 18px; line-height: 25px; font-weight: bold; color: #FFFFFF; text-decoration: none; padding: 15px 15px 15px 15px;">Open Task</a>\n\
    </td>\n\
   </tr>\n\
   <tr>\n\
    <td>\n\
     <p><span style="font-size: 12px; font-weight: normal; font-style: italic; color: #919191;">This is an automatically generated email. Please do not reply to this email.</span></p>\n\
    </td>\n\
   </tr>\n\
  </tbody>\n\
 </table>\n\
</body>\n\
</html>\n\
```

## Door het systeem gegenereerde metagegevens gebruiken in een e-mailbericht {#using-system-generated-metadata-in-an-email-notification}

Een AEM Forms-toepassing bevat verschillende metagegevensvariabelen (sleutelwaardeparen) uit het vak. U kunt deze variabelen in een e-mailsjabloon gebruiken. De waarde van de variabele is gebaseerd op de bijbehorende formuliertoepassing. In de volgende tabel worden alle metagegevensvariabelen weergegeven die in het vak beschikbaar zijn:

<table> 
 <tbody> 
  <tr> 
   <td>Sleutel</td> 
   <td>Beschrijving</td> 
  </tr> 
  <tr> 
   <td>workitem_title</td> 
   <td>Titel van de bijbehorende formuliertoepassing.</td> 
  </tr> 
  <tr> 
   <td>workitem_url</td> 
   <td>URL voor toegang tot de bijbehorende formuliertoepassing.</td> 
  </tr> 
  <tr> 
   <td>workitem_description</td> 
   <td>Beschrijving van de bijbehorende formuliertoepassing.</td> 
  </tr> 
  <tr> 
   <td>workitem_priority</td> 
   <td>Prioriteit opgegeven voor de bijbehorende formuliertoepassing.</td> 
  </tr> 
  <tr> 
   <td>workitem_due_date</td> 
   <td>Datum waarop voor het laatst op de bijbehorende formuliertoepassing is gehandeld.</td> 
  </tr> 
  <tr> 
   <td>workitem_workflow</td> 
   <td>Naam van de workflow die is gekoppeld aan de formuliertoepassing.</td> 
  </tr> 
  <tr> 
   <td>workitem_assign_timestamp</td> 
   <td>Datum en tijdstip waarop het werkstroomitem aan de huidige ontvanger is toegewezen.</td> 
  </tr> 
  <tr> 
   <td>workitem_assignee</td> 
   <td>Naam van de huidige gemachtigde.</td> 
  </tr> 
  <tr> 
   <td>host_prefix</td> 
   <td>URL van de auteurserver. Bijvoorbeeld https://10.41.42.66:4502<br /> </td> 
  </tr> 
  <tr> 
   <td>publish_prefix</td> 
   <td>URL van de publicatieserver. Bijvoorbeeld https://10.41.42.66:4503</td> 
  </tr> 
 </tbody> 
</table>

## Aangepaste metagegevens gebruiken in een e-mailmelding {#using-custom-metadata-in-an-email-notification}

U kunt ook aangepaste metagegevens gebruiken in een e-mailmelding. Aangepaste metagegevens bevatten naast door het systeem gegenereerde metagegevens ook informatie. Zo worden bijvoorbeeld beleidsdetails opgehaald uit een database. U kunt een bundel ECMAScript of OSGi gebruiken om douanemetagegevens in crx-bewaarplaats toe te voegen:

### ECMAScript gebruiken om aangepaste metagegevens {#use-ecmascript-to-add-custom-metadata} toe te voegen

[](https://en.wikipedia.org/wiki/ECMAScript) ECMAScriptis is een scripttaal. Het wordt gebruikt voor client-side scripting en servertoepassingen. Voer de volgende stappen uit om ECMAScript te gebruiken om douanemetagegevens voor een e-mailmalplaatje toe te voegen:

1. Meld u aan bij CRX DE met een beheeraccount. De URL is `https://[server]:[port]/crx/de/index.jsp`

1. Navigeer naar /apps/fd/dashboard/scripts/metadataScripts. Maak een bestand met de extensie .ecma. Bijvoorbeeld usermetadata.ecma

   Als het bovenvermelde pad niet bestaat, maakt u het.

1. Voeg code aan het .ecma dossier toe dat de logica heeft om douanemetagegevens in zeer belangrijke paren te produceren. Met de volgende ECMAScript-code worden bijvoorbeeld aangepaste metagegevens voor een verzekeringspolis gegenereerd:

   ```
   function getUserMetaData()  {
       //Commented lines below provide an overview on how to set user metadata in map and return it.
       var HashMap = Packages.java.util.HashMap;
       var valuesMap = new HashMap();
       valuesMap.put("policyNumber", "2017568972695");
       valuesMap.put("policyHolder", "Adobe Systems");
   
       return valuesMap;
   }
   ```

1. Klik op Alles opslaan. Het script kan nu worden geselecteerd in AEM workflowmodel.

   ![toewijzen-metagegevens](assets/assigntask-metadata.png)

1. (Optioneel) Geef de titel van het script op:

   Als u de titel niet opgeeft, wordt in het veld Aangepaste metagegevens het volledige pad van het ECMAScript-bestand weergegeven. Voer de volgende stappen uit om een betekenisvolle titel voor het script op te geven:

   1. Breid de manuscriptknoop uit, klik **[!UICONTROL jcr:content]** knoop met de rechtermuisknop aan, en klik **[!UICONTROL Mixins]**.
   1. Type mix:titel in Edit Mixins dialoog en klik **+**.
   1. Voeg een eigenschap met de volgende waarden toe.

      | Naam | jcr:titel |
      |---|---|
      | Type | Tekenreeks |
      | Waarde | Geef de titel van het script op. Bijvoorbeeld, douanemetagegevens voor de verzekeringnemer. De opgegeven waarde wordt weergegeven in de taakstap toewijzen. |

### Een OSGi-bundel en Java-interface gebruiken om aangepaste metagegevens toe te voegen {#use-an-osgi-bundle-and-java-interface-to-add-custom-metadata}

U kunt de interface WorkitemUserMetadataService Java gebruiken om aangepaste metagegevens voor e-mailsjablonen toe te voegen. U kunt een bundel OSGi tot stand brengen die de interface van Java WorkitemUserMetadataService gebruikt en het aan de server van AEM Forms opstelt. De metagegevens worden beschikbaar gesteld voor selectie in de stap Taak toewijzen.

Als u een OSGi-bundel met Java-interface wilt maken, voegt u [AEM Forms Client SDK](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) jar en [granite jar](https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.workflow.api/1.0.2/) bestanden toe als externe afhankelijkheden aan het OSGi-bundelproject. U kunt om het even welke winde van Java gebruiken om een bundel te creëren OSGi. De volgende procedure verstrekt stappen om Eclipse te gebruiken om een bundel te creëren OSGi:

1. Open Eclipse IDE. Ga naar Bestand > Nieuw project.

1. Selecteer Geweven project in het scherm Selecteer een wizard en klik op Volgende.

1. Voor het Nieuwe Gemaakt project, houd gebreken, en klik daarna. Selecteer een archetype en klik op Volgende. Bijvoorbeeld maven-archetype-quickstart. Geef Groep-id, Artefact-id, versie en pakket voor het project op en klik op Voltooien. Het project wordt gemaakt.

1. Open het bestand pom.xml voor bewerking en vervang alle inhoud van het bestand door:

   ```
   
   ```

1. Voeg broncode toe die WorkitemUserMetadataService Java-interface gebruikt om aangepaste metagegevens voor e-mailsjablonen toe te voegen. Hieronder ziet u een voorbeeldcode:

   ```java
   package com.aem.impl;
   
   import com.adobe.fd.workspace.service.external.WorkitemUserMetadataService;
   import org.apache.felix.scr.annotations.Component;
   import org.apache.felix.scr.annotations.Properties;
   import org.apache.felix.scr.annotations.Property;
   import org.apache.felix.scr.annotations.Service;
   import org.osgi.framework.Constants;
   
   import java.util.HashMap;
   import java.util.Map;
   
   @Component
   @Service
   @Properties({
           @Property(name = Constants.SERVICE_DESCRIPTION, value = "A sample implementation of a user metadata service."),
           @Property(name = WorkitemUserMetadataService.SERVICE_PROPERTY_LABEL, value = "Default User Metadata Service")})
   
   public class WorkitemUserMetadataServiceImpl
     implements WorkitemUserMetadataService
   {
     public WorkitemUserMetadataServiceImpl() {}
   
     public Map<String, String> getUserMetadataMap()
     {
       HashMap<String, String> metadataMap = null;
       metadataMap = new HashMap();
       metadataMap.put("test_metadata", "tested-interface implementation");
       return metadataMap;
     }
   }
   ```

1. Open een bevelherinnering en navigeer aan de folder die het OSGi bundelproject bevat. Gebruik het volgende bevel om de bundel te creëren OSGi:

   `mvn clean install`

1. Upload de bundel naar een AEM Forms-server. U kunt AEM pakketbeheer gebruiken om de bundel te importeren naar de AEM Forms-server.

Nadat de bundel wordt ingevoerd, kunt u de meta-gegevens in de Assign stap van de Taak selecteren en het gebruiken een e-mailmalplaatje.
