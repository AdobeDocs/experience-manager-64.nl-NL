---
title: Componenten en services Java APIQuick Start (SOAP)
seo-title: Components and Services Java APIQuick Start(SOAP)
description: Gebruik de Componenten en de Diensten Java API Snelle Begin van het Begin om een component op te stellen, de uitvoeringscontext van de dienst te plaatsen, de dienstveiligheid onbruikbaar te maken, de dienst te beginnen, de waarden van de de dienstconfiguratie te wijzigen, en componenten te verwijderen.
seo-description: Use the Components and Services Java API Quick Start to deploy a component, set the execution context of a service, disable service security, start a service, modify service configuration values, and remove components.
uuid: 7d9ade2d-f927-4558-9e80-df08bd572772
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 14f17126-e744-479b-a8e6-24c131615b46
role: Developer
exl-id: 85c77bd4-e424-491f-8db2-73240732a6e4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# Componenten en services Java API Quick Start (SOAP) {#components-and-services-java-apiquick-start-soap}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Java API Quick Start (SOAP) is beschikbaar voor componenten en services.

[Snel starten (SOAP-modus): Een component implementeren met de Java API](components-services-java-api-quick.md#quick-start-soap-mode-deploying-a-component-using-the-java-api)

[Snel starten (SOAP-modus): De uitvoeringscontext van een service instellen met de Java API](components-services-java-api-quick.md#quick-start-soap-mode-setting-the-execution-context-of-a-service-using-the-java-api)

[Snel starten (SOAP-modus): Servicebeveiliging uitschakelen met de Java API](components-services-java-api-quick.md#quick-start-soap-mode-disabling-service-security-using-the-java-api)

[Snel starten (SOAP-modus): Een service starten met de Java API](components-services-java-api-quick.md#quick-start-soap-mode-starting-a-service-using-the-java-api)

[Snel starten (SOAP-modus): De configuratiewaarden van services wijzigen met de Java API](components-services-java-api-quick.md#quick-start-soap-mode-modifying-a-services-configuration-values-using-the-java-api)

[Snel starten (SOAP-modus): Componenten verwijderen met de Java API](components-services-java-api-quick.md#quick-start-soap-mode-removing-components-using-the-java-api)

AEM Forms-bewerkingen kunnen worden uitgevoerd met behulp van de sterk getypte AEM Forms-API en de verbindingsmodus moet worden ingesteld op SOAP.

>[!NOTE]
>
>U kunt componenten en de diensten programmatically niet manipuleren door de Webdiensten te gebruiken.

>[!NOTE]
>
>De snelle aanvang die in Programmering met AEM vormen wordt gevestigd is gebaseerd op de server van Forms die op JBoss en het werkende systeem van Vensters wordt opgesteld. Als u echter een ander besturingssysteem gebruikt, zoals Unix, vervangt u specifieke paden voor vensters door paden die worden ondersteund door het desbetreffende besturingssysteem. Als u een andere J2EE-toepassingsserver gebruikt, moet u ook geldige verbindingseigenschappen opgeven. Zie [Verbindingseigenschappen instellen](/help/forms/developing/invoking-aem-forms-using-java.md#setting-connection-properties).

>[!NOTE]
>
>Als u een douanecomponent hebt en u protocollen gebruikt van de ZEEP of van EJB om DSCs op de zelfde lokale server aan te halen, en die aanroepen ophouden werkend na een verbetering, dan gebruik in-VM ([DSC_IN_VM_PASSTHROUGH_STRATEGY](https://www.adobe.io/experience-manager/reference-materials/6-4/forms/programlc/javadoc/com/adobe/idp/dsc/clientsdk/ServiceClientFactoryProperties.html)) oproepstrategie. Gebruik de aanroepingsmethode van DSC in-VM met standaardServiceClientFactory en construeer geen ServiceClientFactory gebruikend protocollen SOAP of EJB.

## Snel starten (SOAP-modus): Een component implementeren met de Java API {#quick-start-soap-mode-deploying-a-component-using-the-java-api}

In het volgende Java-voorbeeld wordt een component geïmplementeerd die is gebaseerd op een JAR-bestand met de naam *adobe-emailSample-dsc.jar*.

```as3
 /* 
        * This Java Quick Start uses the following JAR files 
        * 1. adobe-taskmanager-client.jar 
        * 2. adobe-livecycle-client.jar 
        * 3. adobe-usermanager-client.jar 
        * 4. activation.jar (required for SOAP mode) 
        * 5. axis.jar (required for SOAP mode) 
        * 6. commons-codec-1.3.jar (required for SOAP mode) 
        * 7. commons-collections-3.2.jar  (required for SOAP mode) 
        * 8. commons-discovery.jar (required for SOAP mode) 
        * 9. commons-logging.jar (required for SOAP mode) 
        * 10. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
        * 11. jaxen-1.1-beta-9.jar (required for SOAP mode) 
        * 12. jaxrpc.jar (required for SOAP mode) 
        * 13. log4j.jar (required for SOAP mode) 
        * 14. mail.jar (required for SOAP mode) 
        * 15. saaj.jar (required for SOAP mode) 
        * 16. wsdl4j.jar (required for SOAP mode) 
        * 17. xalan.jar (required for SOAP mode) 
        * 18. xbean.jar (required for SOAP mode) 
        * 19. xercesImpl.jar (required for SOAP mode)
        * The JBoss files must be kept in the jboss\client folder. You can copy the client folder to  
        * your local development environment and then include the 3 JBoss JAR files in your class path 
        * 
        * These JAR files are located in the following path: 
        * <install directory>/sdk/client-libs/common 
        * 
        * The adobe-utilities.jar file is located in the following path: 
        * <install directory>/sdk/client-libs/jboss 
        * 
        * The jboss-client.jar file is located in the following path: 
        * <install directory>/jboss/bin/client 
        * 
        * If you want to invoke a remote forms server instance and there is a 
        * firewall between the client application and the server, then it is  
        * recommended that you use the SOAP mode. When using the SOAP mode,  
        * you have to include additional JAR files located in the following  
        * path 
        * <install directory>/sdk/client-libs/thirdparty 
        * 
        * For information about the SOAP  
        * mode and the additional JAR files that need to be included,  
        * see "Setting connection properties" in Programming  
        * with AEM Forms 
     */ 
 import java.io.FileInputStream; 
 import java.util.*; 
  
 import com.adobe.idp.Document; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.idp.dsc.registry.component.client.*; 
 import com.adobe.idp.dsc.registry.infomodel.Component; 
  
 public class DeployComponents { 
  
     public static void main(String[] args) { 
          
         try{ 
          
             //Set connection properties required to invoke AEM Forms                                 
             Properties connectionProps = new Properties(); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
                          
             //Create a ServiceClientFactory object 
             ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
  
             //Create a ComponentRegistryClient object 
             ComponentRegistryClient    componentReg = new ComponentRegistryClient(myFactory);  
              
             //Reference a JAR file that represents the component to deploy 
         //    FileInputStream componentFile = new FileInputStream("C:\\Adobe\adobe-emailSample-dsc.jar");  
              
             FileInputStream componentFile = new FileInputStream("C:\\A22\Bank.jar");  
             Document component = new Document(componentFile);  
              
             //Install the component 
             Component myComponent = componentReg.install(component); 
             componentReg.start(myComponent); 
              
             System.out.println("The component has been deployed");  
             } 
              
         catch(Exception e) 
         { 
             e.printStackTrace(); 
         } 
     } 
 } 
  
 
```

## Snel starten (SOAP-modus): De uitvoeringscontext van een service instellen met de Java API {#quick-start-soap-mode-setting-the-execution-context-of-a-service-using-the-java-api}

In het volgende Java-codevoorbeeld wordt de uitvoeringscontext van Run-As Invoker ingesteld op een voorbeeldservice met de naam *EncryptDocument*.

```as3
 /* 
        * This Java Quick Start uses the following JAR files 
        * 1. adobe-taskmanager-client.jar 
        * 2. adobe-livecycle-client.jar 
        * 3. adobe-usermanager-client.jar  
        * 4. activation.jar (required for SOAP mode) 
        * 5. axis.jar (required for SOAP mode) 
        * 6. commons-codec-1.3.jar (required for SOAP mode) 
        * 7. commons-collections-3.2.jar  (required for SOAP mode) 
        * 8. commons-discovery.jar (required for SOAP mode) 
        * 9. commons-logging.jar (required for SOAP mode) 
        * 10. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
        * 11. jaxen-1.1-beta-9.jar (required for SOAP mode) 
        * 12. jaxrpc.jar (required for SOAP mode) 
        * 13. log4j.jar (required for SOAP mode) 
        * 14. mail.jar (required for SOAP mode) 
        * 15. saaj.jar (required for SOAP mode) 
        * 16. wsdl4j.jar (required for SOAP mode) 
        * 17. xalan.jar (required for SOAP mode) 
        * 18. xbean.jar (required for SOAP mode) 
        * 19. xercesImpl.jar (required for SOAP mode) 
        * The JBoss files must be kept in the jboss\bin\client folder. You can copy the client folder to  
        * your local development environment and then include the 3 JBoss JAR files in your class path 
        * 
        * These JAR files are located in the following path: 
        * <install directory>/sdk/client-libs/common 
        * 
        * 
        * 
        * If you want to invoke a remote forms server instance and there is a 
        * firewall between the client application and the server, then it is  
        * recommended that you use the SOAP mode. When using the SOAP mode,  
        * you have to include additional JAR files located in the following  
        * path 
        * <install directory>/sdk/client-libs/thirdparty 
        * 
        * For information about the SOAP  
        * mode and the additional JAR files that need to be included,  
        * see "Setting connection properties" in Programming  
        * with AEM Forms 
     */ 
 import java.util.*; 
  
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.idp.dsc.registry.infomodel.ServiceConfiguration; 
 import com.adobe.idp.dsc.registry.service.ModifyServiceConfigurationInfo; 
 import com.adobe.idp.dsc.registry.service.client.ServiceRegistryClient; 
  
 /* 
     * This Java quick start sets the Run-As Invoker to a service named EncryptDocument 
     */ 
 public class SetRunAsConfiguration { 
      
      public static void main(String[] args) { 
  
     try{ 
         //Set connection properties required to invoke AEM Forms 
         Properties connectionProps = new Properties(); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "tblue"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
          
         //Create a ServiceRegistryClient object      
         ServiceClientFactory _factory = ServiceClientFactory.createInstance(connectionProps); 
         ServiceRegistryClient _src = new ServiceRegistryClient(_factory); 
          
         //Reference the EncryptDocument service 
         ServiceConfiguration _config  = _src.getHeadActiveConfiguration("EncryptDocument"); 
          
         //Set the RUN_AS_INVOKER execution context 
         ModifyServiceConfigurationInfo _configModifyInfo = new ModifyServiceConfigurationInfo(); 
         _configModifyInfo.setServiceId(_config.getServiceId()); 
         _configModifyInfo.setMajorVersion(_config.getMajorVersion()); 
         _configModifyInfo.setMinorVersion(_config.getMinorVersion()); 
         _configModifyInfo.setRunAsConfiguration(ServiceConfiguration.RUN_AS_INVOKER); 
         _config = _src.modifyConfiguration(_configModifyInfo); 
     }catch (Exception e) { 
          e.printStackTrace(); 
         }     
     } 
 } 
 
```

## Snel starten (SOAP-modus): Servicebeveiliging uitschakelen met de Java API {#quick-start-soap-mode-disabling-service-security-using-the-java-api}

In het volgende Java-codevoorbeeld wordt de beveiliging uitgeschakeld van de voorbeeldservice EncryptDocument en de services die vanuit deze service worden aangeroepen (de services Waarde instellen en Versleuteling).

```as3
 /* 
        * This Java Quick Start uses the following JAR files 
        * 1. adobe-taskmanager-client.jar 
        * 2. adobe-livecycle-client.jar 
        * 3. adobe-usermanager-client.jar 
        * 4. activation.jar (required for SOAP mode) 
        * 5. axis.jar (required for SOAP mode) 
        * 6. commons-codec-1.3.jar (required for SOAP mode) 
        * 7. commons-collections-3.2.jar  (required for SOAP mode) 
        * 8. commons-discovery.jar (required for SOAP mode) 
        * 9. commons-logging.jar (required for SOAP mode) 
        * 10. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
        * 11. jaxen-1.1-beta-9.jar (required for SOAP mode) 
        * 12. jaxrpc.jar (required for SOAP mode) 
        * 13. log4j.jar (required for SOAP mode) 
        * 14. mail.jar (required for SOAP mode) 
        * 15. saaj.jar (required for SOAP mode) 
        * 16. wsdl4j.jar (required for SOAP mode) 
        * 17. xalan.jar (required for SOAP mode) 
        * 18. xbean.jar (required for SOAP mode) 
        * 19. xercesImpl.jar (required for SOAP mode) 
* 
        * The JBoss files must be kept in the jboss\client folder. You can copy the client folder to 
        * your local development environment and then include the 3 JBoss JAR files in your class path 
        * 
        * These JAR files are located in the following path: 
        * <install directory>/sdk/client-libs/common 
        * 
        * The adobe-utilities.jar file is located in the following path: 
        * <install directory>/sdk/client-libs/jboss 
        * 
        * The jboss-client.jar file is located in the following path: 
        * <install directory>/jboss/bin/client 
        * 
        * If you want to invoke a remote forms server instance and there is a 
        * firewall between the client application and the server, then it is  
        * recommended that you use the SOAP mode. When using the SOAP mode,  
        * you have to include additional JAR files located in the following  
        * path 
        * <install directory>/sdk/client-libs/thirdparty 
        * 
        * For information about the SOAP  
        * mode and the additional JAR files that need to be included,  
        * see "Setting connection properties" in Programming  
        * with AEM Forms 
     */ 
 import java.util.*; 
  
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.idp.dsc.registry.infomodel.ServiceConfiguration; 
 import com.adobe.idp.dsc.registry.service.ModifyServiceInfo; 
 import com.adobe.idp.dsc.registry.service.client.ServiceRegistryClient; 
  
 /* 
     * This Java quick start disables security from the EncryptDocument process 
     * and each service that is located in this process 
     */ 
 public class DisableSecurity{ 
      
      public static void main(String[] args) { 
  
     try{ 
         //Set connection properties required to invoke AEM Forms                                 
         Properties connectionProps = new Properties(); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
                      
          
         //Create a ServiceRegistryClient object      
         ServiceClientFactory _factory = ServiceClientFactory.createInstance(connectionProps); 
         ServiceRegistryClient _src = new ServiceRegistryClient(_factory); 
          
         //Reference the EncryptDocument process and each service that is  
         //invoked from within the EncryptDocument process 
         ServiceConfiguration encryptDocumentService  = _src.getHeadActiveConfiguration("EncryptDocument"); 
         ServiceConfiguration setValueService  = _src.getHeadActiveConfiguration("SetValue"); 
         ServiceConfiguration encryptionService  = _src.getHeadActiveConfiguration("EncryptionService"); 
          
         //Create a ModifyServiceInfo object 
         ModifyServiceInfo si = new ModifyServiceInfo(); 
          
         //Disable security from the EncryptDocument service 
         si.setId(encryptDocumentService.getServiceId()); 
         si.setSecurityEnabled(false); 
         _src.modifyService(si); 
          
         //Disable security from the SetValue service 
         si.setId(setValueService.getServiceId()); 
         si.setSecurityEnabled(false); 
         _src.modifyService(si); 
          
         //Disable security from the EncryptionService 
         si.setId(encryptionService.getServiceId()); 
         si.setSecurityEnabled(false); 
         _src.modifyService(si); 
              
     }catch (Exception e) { 
          e.printStackTrace(); 
         }     
     } 
 } 
 
```

## Snel starten (SOAP-modus): Een service starten met de Java API {#quick-start-soap-mode-starting-a-service-using-the-java-api}

In het volgende Java-codevoorbeeld wordt een service met de naam *SendEmailService*.

```as3
 package com.adobe.sample.servicemanager; 
  
 /** 
     * This Java Quick Start uses the following JAR files: 
     * 1. adobe-livecycle-client.jar 
     * 2. adobe-usermanager-client.jar 
     * 3. adobe-workflow-client-sdk.jar 
     * 4. adobe-utilities.jar 
     * 5. jboss-client.jar (use a different JAR file if AEM Forms is not deployed on Jboss) 
     * 6. jacorb.jar (use a different JAR file if the forms server is not deployed on JBoss) 
     * 7. jnp-client.jar (use a different JAR file if the forms server is not deployed on JBoss) 
     */ 
 import java.util.*; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.registry.infomodel.ServiceConfiguration; 
 import com.adobe.idp.dsc.registry.service.client.ServiceRegistryClient; 
  
 public class StartService { 
  
     public static void main(String[] args) { 
          
         try{ 
             //Set connection properties required to invoke AEM Forms      
             Properties ConnectionProps = new Properties(); 
             ConnectionProps.setProperty("DSC_DEFAULT_SOAP_ENDPOINT", "https://[server]:[port]"); 
             ConnectionProps.setProperty("DSC_TRANSPORT_PROTOCOL","SOAP");           
             ConnectionProps.setProperty("DSC_SERVER_TYPE", "JBoss"); 
             ConnectionProps.setProperty("DSC_CREDENTIAL_USERNAME", "administrator"); 
             ConnectionProps.setProperty("DSC_CREDENTIAL_PASSWORD", "password"); 
              
             //Create a ServiceClientFactory object 
             ServiceClientFactory myFactory = ServiceClientFactory.createInstance(ConnectionProps); 
  
             //Create a ServiceRegistryClient object 
             ServiceRegistryClient serviceReg = new ServiceRegistryClient(myFactory);  
          
             //Reference the SendEmailService 
             ServiceConfiguration myServiceConfig = serviceReg.getHeadActiveConfiguration("SendEmailService"); 
          
             //Start the SendEmailService 
             serviceReg.start(myServiceConfig); 
             } 
              
                 catch(Exception e) 
                 { 
                     e.printStackTrace(); 
                 } 
     } 
 } 
  
 
```

## Snel starten (SOAP-modus): De configuratiewaarden van services wijzigen met de Java API {#quick-start-soap-mode-modifying-a-services-configuration-values-using-the-java-api}

In het volgende Java-voorbeeld worden configuratiewaarden gewijzigd die horen bij SendEmail Service.

```as3
 /* 
     * This Java Quick Start uses the following JAR files 
        * 1. adobe-taskmanager-client.jar 
        * 2. adobe-livecycle-client.jar 
        * 3. adobe-usermanager-client.jar 
        * 4. activation.jar (required for SOAP mode) 
        * 5. axis.jar (required for SOAP mode) 
        * 6. commons-codec-1.3.jar (required for SOAP mode) 
        * 7. commons-collections-3.2.jar  (required for SOAP mode) 
        * 8. commons-discovery.jar (required for SOAP mode) 
        * 9. commons-logging.jar (required for SOAP mode) 
        * 10. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
        * 11. jaxen-1.1-beta-9.jar (required for SOAP mode) 
        * 12. jaxrpc.jar (required for SOAP mode) 
        * 13. log4j.jar (required for SOAP mode) 
        * 14. mail.jar (required for SOAP mode) 
        * 15. saaj.jar (required for SOAP mode) 
        * 16. wsdl4j.jar (required for SOAP mode) 
        * 17. xalan.jar (required for SOAP mode) 
        * 18. xbean.jar (required for SOAP mode) 
        * 19. xercesImpl.jar (required for SOAP mode) 
        * The JBoss files must be kept in the jboss\client folder. You can copy the client folder to  
        * your local development environment and then include the 3 JBoss JAR files in your class path 
        * 
        * These JAR files are located in the following path: 
        * <install directory>/sdk/client-libs/common 
        * 
        * The adobe-utilities.jar file is located in the following path: 
        * <install directory>/sdk/client-libs/jboss 
        * 
        * The jboss-client.jar file is located in the following path: 
        * <install directory>/jboss/bin/client 
        * 
        * If you want to invoke a remote forms server instance and there is a 
        * firewall between the client application and the server, then it is  
        * recommended that you use the SOAP mode. When using the SOAP mode,  
        * you have to include additional JAR files located in the following  
        * path 
        * <install directory>/sdk/client-libs/thirdparty 
        * 
        * For information about the SOAP  
        * mode and the additional JAR files that need to be included,  
        * see "Setting connection properties" in Programming  
        * with AEM Forms 
     */ 
 import java.util.*; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.registry.infomodel.ConfigParameter; 
 import com.adobe.idp.dsc.registry.infomodel.ServiceConfiguration; 
 import com.adobe.idp.dsc.registry.service.ModifyServiceConfigurationInfo; 
 import com.adobe.idp.dsc.registry.service.client.ServiceRegistryClient; 
  
  
 public class ModifyService { 
  
     public static void main(String[] args) { 
          
         try{ 
             //Set connection properties required to invoke AEM Forms     
             Properties ConnectionProps = new Properties(); 
             ConnectionProps.setProperty("DSC_DEFAULT_SOAP_ENDPOINT", "https://[server]:[port]"); 
             ConnectionProps.setProperty("DSC_TRANSPORT_PROTOCOL","SOAP");           
             ConnectionProps.setProperty("DSC_SERVER_TYPE", "JBoss"); 
             ConnectionProps.setProperty("DSC_CREDENTIAL_USERNAME", "administrator"); 
             ConnectionProps.setProperty("DSC_CREDENTIAL_PASSWORD", "password"); 
              
             //Create a ServiceClientFactory object 
             ServiceClientFactory myFactory = ServiceClientFactory.createInstance(ConnectionProps); 
  
             //Create a ServiceRegistryClient object 
             ServiceRegistryClient serviceReg = new ServiceRegistryClient(myFactory);  
          
             //Reference the SendEmailService 
             ServiceConfiguration myServiceConfig = serviceReg.getHeadServiceConfiguration("SendEmailService"); 
                              
             //Create a ModifyServiceConfigurationInfo object 
                 ModifyServiceConfigurationInfo modService = new ModifyServiceConfigurationInfo(); 
                      
             //Set configuration values required by the SendEmailService 
             String serviceId = myServiceConfig.getServiceId(); 
             modService.setServiceId(serviceId); 
             modService.setMajorVersion(1); 
             modService.setConfigParameterAsText("smtpHost","mySMTPSERVER"); 
             modService.setConfigParameterAsText("smtpUser","smyUserName");     
             modService.setConfigParameterAsText("smtpPassword","myPassword");     
                      
             //Modify the service’s configuration values 
             serviceReg.modifyConfiguration(modService); 
                          
             //Conform the new configuration values 
             ServiceConfiguration serviceConfig = serviceReg.getServiceConfiguration("SendEmailService",1,0); 
             ConfigParameter cp = serviceConfig.getConfigParameter("smtpUser"); 
             String configValue = cp.getTextValue();  
             System.out.println(configValue); 
             } 
      
             catch(Exception e) 
             { 
                 e.printStackTrace(); 
             } 
     } 
 } 
  
  
 
```

## Snel starten (SOAP-modus): Componenten verwijderen met de Java API {#quick-start-soap-mode-removing-components-using-the-java-api}

In het volgende Java-codevoorbeeld wordt een component verwijderd met de Java API.

```as3
 /* 
     * This Java Quick Start uses the following JAR files 
     * 1. adobe-taskmanager-client.jar 
     * 2. adobe-livecycle-client.jar 
     * 3. adobe-usermanager-client.jar 
     * 4. adobe-utilities.jar 
     * 5. jboss-client.jar (use a different JAR file if the forms server is not deployed 
     * on JBoss) 
     * 6. commons-code-1.3.jar 
     * 7. adobe-workflow-client-sdk.jar 
     * 8. jacorb.jar (use a different JAR file if the forms server is not deployed on JBoss) 
     * 9. jnp-client.jar (use a different JAR file if the forms server is not deployed on JBoss) 
     * 
     * The JBoss files must be kept in the jboss\client folder. You can copy the client folder to  
     * your local development environment and then include the 3 JBoss JAR files in your class path 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * The adobe-utilities.jar file is located in the following path: 
     * <install directory>/sdk/client-libs/jboss 
     * 
     * The jboss-client.jar file is located in the following path: 
     * <install directory>/jboss/bin/client 
     * 
     * If you want to invoke a remote forms server instance and there is a 
     * firewall between the client application and the server, then it is  
     * recommended that you use the SOAP mode. When using the SOAP mode,  
     * you have to include additional JAR files located in the following  
     * path 
     * <install directory>/sdk/client-libs/thirdparty 
     * 
     * For information about the SOAP  
     * mode and the additional JAR files that need to be included,  
     * see "Setting connection properties" in Programming  
     * with AEM Forms 
     */ 
 import java.util.*; 
  
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.idp.dsc.registry.component.client.*; 
 import com.adobe.idp.dsc.registry.infomodel.Component; 
  
 public class RemoveComponent { 
  
     public static void main(String[] args) { 
          
         try{ 
               //Set connection properties required to invoke AEM Forms                                                                                                                        
               Properties connectionProps = new Properties(); 
               connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
      connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
               connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
               connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
               connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
              
             //Create a ServiceClientFactory object 
             ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
  
             //Create a ComponentRegistryClient object 
             ComponentRegistryClient    componentReg = new ComponentRegistryClient(myFactory);  
              
             //Retrieve the Id of the component to remove from the service container 
             Component myComponent = componentReg.getComponent("com.adobe.livecycle.sample.email.emailSampleComponent", "1.0"); 
              
             //Determine if the component is in a running state 
             if (myComponent.getState()== Component.RUNNING) 
             { 
                 //Stop the component 
                 Component stoppedComponent = componentReg.stop(myComponent); 
                  
                 //Uninstall the component 
                 componentReg.uninstall(stoppedComponent); 
             } 
             else 
                 componentReg.uninstall(myComponent); 
                  
             System.out.println("The component was removed."); 
             } 
              
             catch(Exception e) 
             { 
                 e.printStackTrace(); 
             } 
     } 
 } 
  
  
 
```
