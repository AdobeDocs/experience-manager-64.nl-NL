---
title: Java API Quick Start (SOAP) voor gebruikersbeheer
seo-title: User Manager Java API Quick Start(SOAP)
description: De Manager API van de Gebruiker van het gebruik om gebruikers toe te voegen, gebruikers te schrappen, groepen tot stand te brengen, gebruikers en groepen te leiden, rollen en toestemmingen te beheren, gebruikers programmatically te synchroniseren, en de Knoop van de Voorkeur te beheren programmatically.
seo-description: Use User Manager API to add users, delete users, create groups, manage users and groups, manage roles and permissions, synchronize users programmatically, and manage the Preferences Nodes programmatically.
uuid: 0a2aa4ab-9329-485f-a30e-47bb471ce1b5
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: e0c20fd2-b084-4f61-936c-5282826a8d3d
role: Developer
exl-id: 130b5669-4533-4e88-9a64-bbbd7c68a5ca
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Java API Quick Start (SOAP) voor gebruikersbeheer {#user-manager-java-api-quick-start-soap}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Java API Quick Start (SOAP) is beschikbaar voor de gebruikersbeheer-API.

[Snel starten (SOAP-modus): Gebruikers toevoegen met de Java API](user-manager-java-api-quick.md#quick-start-soap-mode-adding-users-using-the-java-api)

[Snel starten (SOAP-modus): Gebruikers verwijderen met de Java API](user-manager-java-api-quick.md#quick-start-soap-mode-deleting-users-using-the-java-api)

[Snel starten (SOAP-modus): Groepen maken met de Java API](user-manager-java-api-quick.md#quick-start-soap-mode-creating-groups-using-the-java-api)

[Snel starten (SOAP-modus): Gebruikers en groepen beheren met de Java API](user-manager-java-api-quick.md#quick-start-soap-mode-managing-users-and-groups-using-the-java-api)

[Snel starten (SOAP-modus): Rollen en machtigingen beheren met de Java API](user-manager-java-api-quick.md#quick-start-soap-mode-managing-roles-and-permissions-using-the-java-api)

[Snel starten (SOAP-modus): Gebruikers programmatisch synchroniseren met de Java API](user-manager-java-api-quick.md#quick-start-soap-mode-programmatically-synchronizing-users-using-the-java-api)

[Snel starten (SOAP-modus): De voorkeursknooppunten via programmacode beheren met de Java API](user-manager-java-api-quick.md#quick-start-soap-mode-programmatically-managing-the-preferences-nodes-using-the-java-api)

AEM Forms-bewerkingen kunnen worden uitgevoerd met behulp van de sterk getypte AEM Forms-API en de verbindingsmodus moet worden ingesteld op SOAP.

>[!NOTE]
>
>De snelle start in Programmeren met AEM formulieren is gebaseerd op het document als u een ander besturingssysteem gebruikt, zoals Unix, vervangt Windows-specifieke paden door paden die door het toepasselijke besturingssysteem worden ondersteund. Als u een andere J2EE-toepassingsserver gebruikt, moet u ook geldige verbindingseigenschappen opgeven. Zie [Verbindingseigenschappen instellen](/help/forms/developing/invoking-aem-forms-using-java.md#setting-connection-properties).


## Snel starten (SOAP-modus): Gebruikers toevoegen met de Java API {#quick-start-soap-mode-adding-users-using-the-java-api}

In het volgende codevoorbeeld wordt een gebruiker met de naam Wendy Blue aan AEM Forms toegevoegd. (Zie [Gebruikers toevoegen](/help/forms/developing/users.md#adding-users).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-livecycle-client.jar 
     * 2. adobe-usermanager-client.jar 
    * 3. activation.jar (required for SOAP mode) 
    * 4. axis.jar (required for SOAP mode) 
    * 5. commons-codec-1.3.jar (required for SOAP mode) 
    * 6. commons-collections-3.2.jar  (required for SOAP mode) 
    * 7. commons-discovery.jar (required for SOAP mode) 
    * 8. commons-logging.jar (required for SOAP mode) 
    * 9. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
    * 10. jaxen-1.1-beta-9.jar (required for SOAP mode) 
    * 11. jaxrpc.jar (required for SOAP mode) 
    * 12. log4j.jar (required for SOAP mode) 
    * 13. mail.jar (required for SOAP mode) 
    * 14. saaj.jar (required for SOAP mode) 
    * 15. wsdl4j.jar (required for SOAP mode) 
    * 16. xalan.jar (required for SOAP mode) 
    * 17. xbean.jar (required for SOAP mode) 
    * 18. xercesImpl.jar (required for SOAP mode) 
     * 
     * The JBoss files must be kept in the jboss\client folder. You can copy the client folder to  
     * your local development environment and then include the 3 JBoss JAR files in your class path 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * 
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
     * 
     * For complete details about the location of the AEM Forms JAR files,  
     * see "Including AEM Forms Java library files" in Programming  
     * with AEM Forms 
     */ 
  
 import java.util.*; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.livecycle.usermanager.client.DirectoryManagerServiceClient; 
 import com.adobe.idp.um.api.infomodel.impl.*; 
 import com.adobe.idp.um.api.infomodel.*; 
  
 public class AddUser { 
  
     public static void main(String[] args) { 
         try { 
             //Set connection properties required to invoke AEM Forms                                            
                Properties connectionProps = new Properties(); 
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
      connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
  
             //Create a ServiceClientFactory object 
             ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
  
             //Create an DirectoryManagerServiceClient object 
             DirectoryManagerServiceClient dmClient = new DirectoryManagerServiceClient(myFactory); 
              
             //Create a User object and populate its attributes  
             UserImpl u = new UserImpl(); 
             u.setDomainName("DefaultDom");  
             u.setUserid("wblue");  
             u.setCanonicalName("wblue");  
             u.setPrincipalType("USER");  
             u.setGivenName("Wendy");  
             u.setFamilyName("Blue");  
             u.setLocale(Locale.CANADA); 
             u.setTimezone(TimeZone.getDefault()); 
             u.setDisabled(false); 
              
             //Add the User to the system using the DirectoryManagerServiceClient 
             dmClient.createLocalUser(u,"password"); 
              
             //Ensure that the user was added  
             //Create a PrincipalSearchFilter to find the user by ID 
             PrincipalSearchFilter psf = new PrincipalSearchFilter(); 
             psf.setUserId("wblue"); 
             List<User> principalList = dmClient.findPrincipals(psf); 
             Iterator<User> pit = principalList.iterator(); 
             if(pit.hasNext()){ 
                 User theUser = pit.next(); 
                 System.out.println("User ID: " + theUser.getUserid()); 
                 System.out.println("User name: " + theUser.getGivenName() +" "+ theUser.getFamilyName()); 
                 System.out.println("User Domain: " + theUser.getDomainName()); 
                 System.out.println("is user disabled?: " + theUser.isDisabled()); 
             } 
              
         }catch (Exception e) { 
             e.printStackTrace(); 
         } 
 ; 
     } 
  
 } 
  
 
```

## Snel starten (SOAP-modus): Gebruikers verwijderen met de Java API {#quick-start-soap-mode-deleting-users-using-the-java-api}

In het volgende codevoorbeeld wordt een gebruiker met de naam Wendy Blue uit AEM Forms verwijderd. (Zie [Gebruikers verwijderen](/help/forms/developing/users.md#deleting-users).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-livecycle-client.jar 
     * 2. adobe-usermanager-client.jar 
    * 3. activation.jar (required for SOAP mode) 
    * 4. axis.jar (required for SOAP mode) 
    * 5. commons-codec-1.3.jar (required for SOAP mode) 
    * 6. commons-collections-3.2.jar  (required for SOAP mode) 
    * 7. commons-discovery.jar (required for SOAP mode) 
    * 8. commons-logging.jar (required for SOAP mode) 
    * 9. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
    * 10. jaxen-1.1-beta-9.jar (required for SOAP mode) 
    * 11. jaxrpc.jar (required for SOAP mode) 
    * 12. log4j.jar (required for SOAP mode) 
    * 13. mail.jar (required for SOAP mode) 
    * 14. saaj.jar (required for SOAP mode) 
    * 15. wsdl4j.jar (required for SOAP mode) 
    * 16. xalan.jar (required for SOAP mode) 
    * 17. xbean.jar (required for SOAP mode) 
    * 18. xercesImpl.jar (required for SOAP mode) 
     * 
     * The JBoss files must be kept in the jboss\client folder. You can copy the client folder to  
     * your local development environment and then include the 3 JBoss JAR files in your class path 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * 
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
     * 
     * For complete details about the location of the AEM Forms JAR files,  
     * see "Including AEM Forms Java library files" in Programming  
     * with AEM Forms 
     */ 
 import java.util.*; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.idp.um.api.infomodel.PrincipalSearchFilter; 
 import com.adobe.idp.um.api.infomodel.User; 
 import com.adobe.livecycle.usermanager.client.DirectoryManagerServiceClient; 
  
 public class DeleteUser { 
  
     public static void main(String[] args) { 
         try { 
             //Set connection properties required to invoke AEM Forms 
             Properties connectionProps = new Properties(); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL, ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, ServiceClientFactoryProperties.DSC_JBOSS_SERVER_TYPE); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
  
             // Create a ServiceClientFactory object 
             ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
              
             // Create a DirectoryManagerServiceClient object 
             DirectoryManagerServiceClient dm = new DirectoryManagerServiceClient(myFactory); 
              
             //Find the target user by the user ID value 
             PrincipalSearchFilter psf = new PrincipalSearchFilter(); 
             psf.setUserId("wblue"); 
             List<User> principalList = dm.findPrincipals(psf); 
             Iterator<User> pit = principalList.iterator(); 
              
             //Delete the user 
             while(pit.hasNext()){ 
                 User targetUser = pit.next(); 
                 dm.deleteLocalUser(targetUser.getOid()); 
             } 
         } catch (Exception e) { 
             e.printStackTrace(); 
         } 
     } 
 } 
 
```

## Snel starten (SOAP-modus): Gebruikers en groepen beheren met de Java API {#quick-start-soap-mode-managing-users-and-groups-using-the-java-api}

In het volgende codevoorbeeld worden een lokale gebruiker en de lokale groep gevonden waartoe de gebruiker behoort. (Zie [Gebruikers en groepen beheren](/help/forms/developing/users.md#managing-users-and-groups).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-livecycle-client.jar 
     * 2. adobe-usermanager-client.jar 
    * 3. activation.jar (required for SOAP mode) 
    * 4. axis.jar (required for SOAP mode) 
    * 5. commons-codec-1.3.jar (required for SOAP mode) 
    * 6. commons-collections-3.2.jar  (required for SOAP mode) 
    * 7. commons-discovery.jar (required for SOAP mode) 
    * 8. commons-logging.jar (required for SOAP mode) 
    * 9. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
    * 10. jaxen-1.1-beta-9.jar (required for SOAP mode) 
    * 11. jaxrpc.jar (required for SOAP mode) 
    * 12. log4j.jar (required for SOAP mode) 
    * 13. mail.jar (required for SOAP mode) 
    * 14. saaj.jar (required for SOAP mode) 
    * 15. wsdl4j.jar (required for SOAP mode) 
    * 16. xalan.jar (required for SOAP mode) 
    * 17. xbean.jar (required for SOAP mode) 
    * 18. xercesImpl.jar (required for SOAP mode) 
     * 
     * The JBoss files must be kept in the jboss\client folder. You can copy the client folder to  
     * your local development environment and then include the 3 JBoss JAR files in your class path 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * 
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
     * 
     * For complete details about the location of the AEM FOrms JAR files,  
     * see "Including AEM Forms Java library files" in Programming  
     * with AEM Forms 
     */ 
 import java.util.*; 
  
 import com.adobe.idp.um.api.infomodel.*; 
 import com.adobe.livecycle.usermanager.client.DirectoryManagerServiceClient; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
  
 public class ManageUsersAndGroupsTest 
 { 
     public static void main(String[] args) { 
         try { 
             //Set connection properties required to invoke AEM Forms                      
             Properties connectionProps = new Properties(); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
  
             //Create a ServiceClientFactory object 
             ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
  
             // Create an DirectoryManagerServiceClient object 
             DirectoryManagerServiceClient dirClient = new DirectoryManagerServiceClient(myFactory); 
  
             // Find a local user 
             PrincipalSearchFilter psf = new PrincipalSearchFilter(); 
             psf.setUserId("wblue"); 
             List principalList = dirClient.findPrincipals(psf); 
             Iterator pit = principalList.iterator(); 
             String oid = ""; 
             User testUser = null; 
             if (pit.hasNext()) 
             { 
                 // Obtain the principal’s object identifier 
                 testUser = (User)(pit.next()); 
             } 
              
             // Find the local group 
             Set groupMemberships = testUser.getGroupMemberships(); 
             Iterator git = groupMemberships.iterator(); 
             Group localGroup = null; 
             if (git.hasNext()) 
             { 
                 // Obtain the group to which the user belongs 
                 localGroup = (Group)(git.next()); 
             } 
              
             // Determine the domain and the group to which the local user belongs 
             String verifyCanonicalName = testUser.getCanonicalName(); 
             Domain verifyDomain = dirClient.findDomain(testUser.getDomainName()); 
             String verifyDomainName = verifyDomain.getDomainName(); 
             Group verifyGroup = dirClient.getDomainAsGroup(verifyDomainName); 
             String verifyGroupName = verifyGroup.getCanonicalName(); 
  
             // Print the uniquely identifying information about the user 
             System.out.println("User name: " + verifyCanonicalName); 
             System.out.println("Group name: " + verifyGroupName); 
             System.out.println("Domain names should match: " + verifyDomainName + ", "+ testUser.getDomainName()); 
          
         } 
         catch (Exception e) 
         { 
             System.out.println("Error occurred: " + e.getMessage()); 
         } 
     }  
 } 
  
  
 
```

## Snel starten (SOAP-modus): Rollen en machtigingen beheren met de Java API {#quick-start-soap-mode-managing-roles-and-permissions-using-the-java-api}

Het volgende codevoorbeeld wijst de rol van de Gebruiker van de Diensten aan een hoofd toe, drukt de rollen het hoofd heeft, en verwijdert dan de rol uit het hoofd. Voor deze snelle start worden twee services aangeroepen: de dienst DirectoryManager en de dienst AuthorizationManager.(Zie [Rollen en machtigingen beheren](/help/forms/developing/users.md#managing-roles-and-permissions).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-livecycle-client.jar 
     * 2. adobe-usermanager-client.jar 
    * 3. activation.jar (required for SOAP mode) 
    * 4. axis.jar (required for SOAP mode) 
    * 5. commons-codec-1.3.jar (required for SOAP mode) 
    * 6. commons-collections-3.2.jar  (required for SOAP mode) 
    * 7. commons-discovery.jar (required for SOAP mode) 
    * 8. commons-logging.jar (required for SOAP mode) 
    * 9. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
    * 10. jaxen-1.1-beta-9.jar (required for SOAP mode) 
    * 11. jaxrpc.jar (required for SOAP mode) 
    * 12. log4j.jar (required for SOAP mode) 
    * 13. mail.jar (required for SOAP mode) 
    * 14. saaj.jar (required for SOAP mode) 
    * 15. wsdl4j.jar (required for SOAP mode) 
    * 16. xalan.jar (required for SOAP mode) 
    * 17. xbean.jar (required for SOAP mode) 
    * 18. xercesImpl.jar (required for SOAP mode) 
     * 
     * The JBoss files must be kept in the jboss\client folder. You can copy the client folder to  
     * your local development environment and then include the 3 JBoss JAR files in your class path 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * 
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
     * 
     * For complete details about the location of the AEM Forms JAR files,  
     * see "Including AEM Forms Java library files" in Programming  
     * with AEM Forms 
     */ 
  
 import java.util.*; 
  
 import com.adobe.idp.um.api.infomodel.*; 
 import com.adobe.livecycle.usermanager.client.AuthorizationManagerServiceClient; 
 import com.adobe.livecycle.usermanager.client.DirectoryManagerServiceClient; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
  
 public class ManageRolesAndPermissionsTest 
 { 
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
  
             // Create an AuthorizationManagerServiceClient object 
             AuthorizationManagerServiceClient amClient = new AuthorizationManagerServiceClient(myFactory); 
  
             // Retrieve a principal 
             DirectoryManagerServiceClient dirClient = new DirectoryManagerServiceClient(myFactory); 
             PrincipalSearchFilter psf = new PrincipalSearchFilter(); 
             psf.setUserId("wblue"); 
             List principalList = dirClient.findPrincipals(psf); 
             Iterator pit = principalList.iterator(); 
             String oid = ""; 
             if (pit.hasNext()) 
             { 
                 // Obtain the principal’s object identifier 
                 oid = ((User)pit.next()).getOid(); 
                 String[] principalOids = new String[1]; 
                 principalOids[0] = oid; 
  
                 //Obtain the roles to be assigned 
                 RoleSearchFilter rsf = new RoleSearchFilter(); 
                 rsf.setRoleName("Services User"); 
                 List roleList = amClient.findRoles(rsf); 
                 Iterator rit = roleList.iterator(); 
                 String roleId1 = ""; 
                 if (rit.hasNext()) 
                 { 
                     // Obtain the role identifier 
                     roleId1 = ((Role)rit.next()).getId(); 
  
                     // Assign the role to the principal 
                     amClient.assignRole(roleId1, principalOids); 
                 } 
                 else 
                 { 
                     System.out.println("Role not found"); 
                 } 
  
                 // Determine which roles the principal has 
                 Set roleSet = amClient.findRolesForPrincipal(oid); 
  
                 // Print the roles the principal has 
                 Iterator it = roleSet.iterator(); 
                 Role r = null; 
                 System.out.println("Roles:"); 
                 while (it.hasNext()) 
                 { 
                     r = ((Role)it.next()); 
                     System.out.println(r.getName()); 
                 } 
  
                 // Remove a role from the principal 
                 //amClient.unassignRole(roleId1, principalOids); 
             } 
             else 
             { 
                 System.out.println("Principal not found"); 
             } 
  
         }catch (Exception e) { 
             e.printStackTrace(); 
         } 
     } 
 } 
  
  
 
```

## Snel starten (SOAP-modus): Gebruikers programmatisch synchroniseren met de Java API {#quick-start-soap-mode-programmatically-synchronizing-users-using-the-java-api}

In het volgende Java-codevoorbeeld worden gebruikers gesynchroniseerd met de API&#39;s voor gebruikersbeheer. (Zie [Gebruikers programmatisch synchroniseren](/help/forms/developing/users.md#programmatically-synchronizing-users).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-livecycle-client.jar 
     * 2. adobe-usermanager-client.jar 
    * 3. activation.jar (required for SOAP mode) 
    * 4. axis.jar (required for SOAP mode) 
    * 5. commons-codec-1.3.jar (required for SOAP mode) 
    * 6. commons-collections-3.2.jar  (required for SOAP mode) 
    * 7. commons-discovery.jar (required for SOAP mode) 
    * 8. commons-logging.jar (required for SOAP mode) 
    * 9. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
    * 10. jaxen-1.1-beta-9.jar (required for SOAP mode) 
    * 11. jaxrpc.jar (required for SOAP mode) 
    * 12. log4j.jar (required for SOAP mode) 
    * 13. mail.jar (required for SOAP mode) 
    * 14. saaj.jar (required for SOAP mode) 
    * 15. wsdl4j.jar (required for SOAP mode) 
    * 16. xalan.jar (required for SOAP mode) 
    * 17. xbean.jar (required for SOAP mode) 
    * 18. xercesImpl.jar (required for SOAP mode) 
     * 19. adobe-usermanager-util-client.jar 
     * 
     * The JBoss files must be kept in the jboss\client folder. You can copy the client folder to  
     * your local development environment and then include the 3 JBoss JAR files in your class path 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * 
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
     * 
     * For complete details about the location of the AEM Forms JAR files,  
     * see "Including AEM Forms Java library files" in Programming  
     * with AEM Forms 
     */ 
  
 import java.util.*; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.livecycle.usermanager.client.DirectoryManagerServiceClient; 
 import com.adobe.idp.um.api.DirectoryManager; 
 import com.adobe.idp.um.api.infomodel.DirectorySyncInfo; 
 import com.adobe.idp.um.dsc.util.client.UserManagerUtilServiceClient; 
  
 public class SynchDomain { 
  
     public static void main(String[] args) { 
         try { 
              
             //Set connection properties required to invoke AEM Forms                                            
                Properties connectionProps = new Properties(); 
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
      connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
  
             //Create a UserManagerUtilServiceClient object 
             ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
             UserManagerUtilServiceClient umutil = new  UserManagerUtilServiceClient(myFactory); 
              
             //Specify the set of enterprise domains to synchronize 
             Set<String> domainNames = new HashSet<String>(); 
             domainNames.add("adobe3"); 
  
             //Perform the synchronization operation on the set of enterprise domains specified above 
             umutil.scheduleSynchronization(domainNames); 
  
             //In case the synchronization needs to be performed on all the registered enterprise domains use this method umutil.scheduleSynchronization(); 
              
             DirectoryManager dm = new DirectoryManagerServiceClient(myFactory); 
             Map<String, DirectorySyncInfo> synchStatus = dm.getDirectorySyncStatus(domainNames); 
              
             String domainName = "adobe3"; 
             DirectorySyncInfo di = synchStatus.get(domainName); 
             if(di.getSyncStatus() == DirectorySyncInfo.SYNCSTATUS_COMPLETED){ 
                          System.out.println("Directory synch for domain     "+domainName+" is complete"); 
  
             } 
              
         }catch (Exception e) { 
             e.printStackTrace(); 
         } 
     } 
  
 } 
  
  
 
```

## Snel starten (SOAP-modus): Gebruikers toevoegen met de Java API {#quick_start_soap_mode_adding_users_using_the_java_api-1}

In het volgende codevoorbeeld wordt een gebruiker met de naam Wendy Blue aan AEM Forms toegevoegd. (Zie [Gebruikers toevoegen](/help/forms/developing/users.md#adding-users).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-livecycle-client.jar 
     * 2. adobe-usermanager-client.jar 
    * 3. activation.jar (required for SOAP mode) 
    * 4. axis.jar (required for SOAP mode) 
    * 5. commons-codec-1.3.jar (required for SOAP mode) 
    * 6. commons-collections-3.2.jar  (required for SOAP mode) 
    * 7. commons-discovery.jar (required for SOAP mode) 
    * 8. commons-logging.jar (required for SOAP mode) 
    * 9. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
    * 10. jaxen-1.1-beta-9.jar (required for SOAP mode) 
    * 11. jaxrpc.jar (required for SOAP mode) 
    * 12. log4j.jar (required for SOAP mode) 
    * 13. mail.jar (required for SOAP mode) 
    * 14. saaj.jar (required for SOAP mode) 
    * 15. wsdl4j.jar (required for SOAP mode) 
    * 16. xalan.jar (required for SOAP mode) 
    * 17. xbean.jar (required for SOAP mode) 
    * 18. xercesImpl.jar (required for SOAP mode) 
     * 
     * The JBoss files must be kept in the jboss\client folder. You can copy the client folder to  
     * your local development environment and then include the 3 JBoss JAR files in your class path 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * 
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
     * 
     * For complete details about the location of the AEM Forms JAR files,  
     * see "Including AEM Forms Java library files" in Programming  
     * with AEM Forms 
     */ 
  
 import java.util.*; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.livecycle.usermanager.client.DirectoryManagerServiceClient; 
 import com.adobe.idp.um.api.infomodel.impl.*; 
 import com.adobe.idp.um.api.infomodel.*; 
  
 public class AddUser { 
  
     public static void main(String[] args) { 
         try { 
             //Set connection properties required to invoke AEM Forms 
                Properties connectionProps = new Properties(); 
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
      connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
                connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
  
             //Create a ServiceClientFactory object 
             ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
  
             //Create an DirectoryManagerServiceClient object 
             DirectoryManagerServiceClient dmClient = new DirectoryManagerServiceClient(myFactory); 
              
             //Create a User object and populate its attributes  
             UserImpl u = new UserImpl(); 
             u.setDomainName("DefaultDom");  
             u.setUserid("wblue");  
             u.setCanonicalName("wblue");  
             u.setPrincipalType("USER");  
             u.setGivenName("Wendy");  
             u.setFamilyName("Blue");  
             u.setLocale(Locale.CANADA); 
             u.setTimezone(TimeZone.getDefault()); 
             u.setDisabled(false); 
              
             //Add the User to the system using the DirectoryManagerServiceClient 
             dmClient.createLocalUser(u,"password"); 
              
             //Ensure that the user was added  
             //Create a PrincipalSearchFilter to find the user by ID 
             PrincipalSearchFilter psf = new PrincipalSearchFilter(); 
             psf.setUserId("wblue"); 
             List<User> principalList = dmClient.findPrincipals(psf); 
             Iterator<User> pit = principalList.iterator(); 
             if(pit.hasNext()){ 
                 User theUser = pit.next(); 
                 System.out.println("User ID: " + theUser.getUserid()); 
                 System.out.println("User name: " + theUser.getGivenName() +" "+ theUser.getFamilyName()); 
                 System.out.println("User Domain: " + theUser.getDomainName()); 
                 System.out.println("is user disabled?: " + theUser.isDisabled()); 
             } 
              
         }catch (Exception e) { 
             e.printStackTrace(); 
         } 
 ; 
     } 
  
 } 
  
 
```

## Snel starten (SOAP-modus): Groepen maken met de Java API {#quick-start-soap-mode-creating-groups-using-the-java-api}

In het volgende codevoorbeeld wordt een groep gemaakt met de naam AdobeGroup naar AEM Forms. (Zie [Groepen maken](/help/forms/developing/users.md#creating-groups).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-livecycle-client.jar 
     * 2. adobe-usermanager-client.jar 
    * 3. activation.jar (required for SOAP mode) 
    * 4. axis.jar (required for SOAP mode) 
    * 5. commons-codec-1.3.jar (required for SOAP mode) 
    * 6. commons-collections-3.2.jar  (required for SOAP mode) 
    * 7. commons-discovery.jar (required for SOAP mode) 
    * 8. commons-logging.jar (required for SOAP mode) 
    * 9. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
    * 10. jaxen-1.1-beta-9.jar (required for SOAP mode) 
    * 11. jaxrpc.jar (required for SOAP mode) 
    * 12. log4j.jar (required for SOAP mode) 
    * 13. mail.jar (required for SOAP mode) 
    * 14. saaj.jar (required for SOAP mode) 
    * 15. wsdl4j.jar (required for SOAP mode) 
    * 16. xalan.jar (required for SOAP mode) 
    * 17. xbean.jar (required for SOAP mode) 
    * 18. xercesImpl.jar (required for SOAP mode) 
     * 
     * The JBoss files must be kept in the jboss\client folder. You can copy the client folder to  
     * your local development environment and then include the 3 JBoss JAR files in your class path 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * 
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
     * 
     * For complete details about the location of the AEM Forms JAR files,  
     * see "Including AEM Forms Java library files" in Programming  
     * with AEM Forms 
     */ 
 import java.util.List; 
 import java.util.Properties; 
  
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.idp.um.api.infomodel.Group; 
 import com.adobe.idp.um.api.infomodel.Principal; 
 import com.adobe.idp.um.api.infomodel.PrincipalSearchFilter; 
 import com.adobe.idp.um.api.infomodel.PrincipalReference; 
 import com.adobe.idp.um.api.infomodel.impl.GroupImpl; 
 import com.adobe.livecycle.usermanager.client.DirectoryManagerServiceClient; 
  
 public class AddGroup { 
  
     public static void main(String[] args) { 
          try { 
           
          //Set connection properties that are required to invoke AEM Forms 
          Properties connectionProps = new Properties(); 
                 connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
      connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
                 connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
                 connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
                 connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
  
                  //Create a ServiceClientFactory object 
                  ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
  
                  //Create an DirectoryManagerServiceClient object 
                  DirectoryManagerServiceClient dmClient = new DirectoryManagerServiceClient(myFactory); 
  
                  //Specify the group and domain name 
                  String groupName = "AdobeGroup"; 
                  String domainName = "TestDomain"; 
                   
                  //Check whether the group exists 
                  String groupOid = checkGroupExist(groupName, domainName,dmClient); 
           
                  //The group exists 
                  if(groupOid != null){ 
                      System.out.println("The group exists"); 
                      return; 
                  } 
           
                  //The group does not exist 
                  String groupCanonicalName = groupName; 
  
                  GroupImpl group = new GroupImpl(); 
                  group.setCanonicalName(groupCanonicalName); 
                  group.setDomainName(domainName); 
                  group.setGroupType(Group.GROUPTYPE_PRINCIPALS); 
                  group.setLocal(true); 
                  group.setPrincipalType(Principal.PRINCIPALTYPE_GROUP); 
           
                  groupOid = dmClient.createLocalGroup(group); 
                  System.out.println("Sample group created with name "+groupName); 
  
          }catch (Exception e) { 
                 e.printStackTrace(); 
             } 
  
         } 
      
     /** 
         * Search for a group located in the specified domain 
         */ 
        private static String checkGroupExist(String groupName, String domainName, DirectoryManagerServiceClient directoryManager){ 
          try { 
          PrincipalSearchFilter psf = new PrincipalSearchFilter(); 
            psf.setCommonName(groupName); 
            psf.setSpecificDomainName(domainName); 
      
            //By default the filter causes like search unless you are using the absolute version 
            //Setting this ensures that search is exact 
            psf.setMatchExactCriteria(true); 
      
            //By default search returns obsolete groups also. Set this to ensure that 
            //only active groups are returned 
            psf.setRetrieveOnlyActive();  
      
            //PrincipalReference are lightweight group objects and searching for them is better performance. 
            //If you do not require any other group attribute then use this 
            //mode of search 
            List<PrincipalReference> result = directoryManager.findPrincipalReferences(psf); 
            if(result.isEmpty()){ 
          System.out.println("Sample group with name "+groupName +" does not exist"); 
                return null; 
            }else{ 
                String oid = result.get(0).getOid();  
                System.out.println("Sample group with name "+groupName +" already exists"); 
                return oid; 
            } 
          }catch (Exception e) { 
                e.printStackTrace(); 
            } 
          return ""; 
        } 
 }
```

## Snel starten (SOAP-modus) Voorkeursknooppunten beheren {#quick-start-soap-mode-managing-preferences-nodes}

De volgende Java-codemodellen die het beheer van knooppunten voorkeuren uitvoeren met de API&#39;s voor gebruikersbeheer. ( Zie [Programmaticaal beheer van de knooppunten van de voorkeuren](/help/forms/developing/programmatically-preferences-nodes.md#programmatically-managing-the-preferences-nodes))

```as3
/* 
 * This Java Quick Start uses the SOAP mode and contains the following JAR files 
 * in the class path: 
 * 1. adobe-livecycle-client.jar 
 * 2. adobe-usermanager-client.jar 
    * 3. activation.jar (required for SOAP mode) 
    * 4. axis.jar (required for SOAP mode) 
    * 5. commons-codec-1.3.jar (required for SOAP mode) 
    * 6. commons-collections-3.2.jar  (required for SOAP mode) 
    * 7. commons-discovery.jar (required for SOAP mode) 
    * 8. commons-logging.jar (required for SOAP mode) 
    * 9. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
    * 10. jaxen-1.1-beta-9.jar (required for SOAP mode) 
    * 11. jaxrpc.jar (required for SOAP mode) 
    * 12. log4j.jar (required for SOAP mode) 
    * 13. mail.jar (required for SOAP mode) 
    * 14. saaj.jar (required for SOAP mode) 
    * 15. wsdl4j.jar (required for SOAP mode) 
    * 16. xalan.jar (required for SOAP mode) 
    * 17. xbean.jar (required for SOAP mode) 
    * 18. xercesImpl.jar (required for SOAP mode) 
 * 
 * These JAR files are located in the following path: 
 * <install directory>/Adobe/Adobe_Experience_Manager_forms/sdk/client-libs/common 
 * 
 * <install directory>/Adobe/Adobe_Experience_Manager_forms/sdk/client-libs/jboss 
 * 
 * <install directory>/Adobe/Adobe_Experience_Manager_forms/jboss/bin/client 
 * 
 * If you want to invoke a remote AEM Forms instance and there is a 
 * firewall between the client application and AEM Forms, then it is 
 * recommended that you use the SOAP mode. When using the SOAP mode, 
 * you have to include additional JAR files located in the following 
 * path 
 * <install directory>/Adobe/Adobe_Experience_Manager_forms/sdk/client-libs/thirdparty 
 * 
 * For information about the SOAP 
 * mode and the additional JAR files that need to be included, 
 * see "Setting connection properties" in Programming 
 * with AEM Forms 
 * 
 * For complete details about the location of the AEM Forms JAR files, 
 * see "Including AEM Forms library files" in Programming 
 * with AEM Forms 
 */ 
 
import java.util.*; 
import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
import com.adobe.idp.um.api.UMException; 
import com.adobe.livecycle.usermanager.client.PreferenceManagerServiceClient;

public class ManagePreferences { 
 
    public static void main(String[] args) { 
    //Set connection properties required to invoke AEM Forms 
        Properties connectionProps = new Properties(); 
    connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
    connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);          
    connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
    connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
    connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
     
    //Create a PreferenceManagerServiceClient object 
    ServiceClientFactory factory = ServiceClientFactory.createInstance(connectionProps); 
    PreferenceManagerServiceClient pmutil = new  PreferenceManagerServiceClient(factory); 
     
    //get the preference map for a particular node 
    String path = "/Adobe/LiveCycle/Config/UM/CommonNameOrder"; 
    Map<String, String> map; 
    try { 
        map = pmutil.getPreferences(path);                 
        for(String str:map.keySet()) { 
            //assert on the key as "ReverseOrder" 
            //assert on the value[map.get(str)] as "false” 
        }                 
    } catch (UMException e) { 
        e.printStackTrace(); 
    } 
     
    // set preferences by editing a particular key/value pair of a Node. 
    String path = "/Adobe/LiveCycle/Config/UM/CommonNameOrder"; 
    Map<String, String> map = new HashMap<String, String>(); 
    map.put("ReverseOrder", "true"); 
    try { 
        pmutil.setPreferences(path, map); 
        Map<String, String> map1 = pmutil.getPreferences(path); 
        for(String str:map1.keySet()) { 
            //assert on the key as "ReverseOrder" 
            //assert on the value[map.get(str)] as "true" 
        }     
    } catch (UMException e) { 
        e.printStackTrace(); 
    } 
    } 
}
```

## Snel starten (SOAP-modus): De voorkeursknooppunten via programmacode beheren met de Java API {#quick-start-soap-mode-programmatically-managing-the-preferences-nodes-using-the-java-api}

De volgende Java-codemodellen die het beheer van voorkeuren uitvoeren met de API&#39;s voor gebruikersbeheer ( Zie [Programmaticaal beheer van de knooppunten van de voorkeuren](/help/forms/developing/programmatically-preferences-nodes.md#programmatically-managing-the-preferences-nodes))

```as3
/* 
 * This Java Quick Start uses the SOAP mode and contains the following JAR files 
 * in the class path: 
 * 1. adobe-livecycle-client.jar 
 * 2. adobe-usermanager-client.jar 
 * 
 * These JAR files are located in the following path: 
 * <install directory>/Adobe/Adobe_Experience_Manager_forms/sdk/client-libs/common 
 * 
 * <install directory>/Adobe/Adobe_Experience_Manager_forms/sdk/client-libs/jboss 
 * 
 * <install directory>/Adobe/Adobe_Experience_Manager_forms/jboss/bin/client 
 * 
 * If you want to invoke a remote AEM Forms instance and there is a 
 * firewall between the client application and AEM FOrms, then it is 
 * recommended that you use the SOAP mode. When using the SOAP mode, 
 * you have to include additional JAR files located in the following 
 * path 
 * <install directory>/Adobe/Adobe_Experience_Manager_forms/sdk/client-libs/thirdparty 
 * 
 * For information about the SOAP 
 * mode and the additional JAR files that need to be included, 
 * see "Setting connection properties" in Programming 
 * with AEM Forms 
 * 
 * For complete details about the location of the AEM Forms JAR files, 
 * see "Including AEM FOrms library files" in Programming 
 * with AEM FOrms 
 */ 
 
import java.util.*; 
import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
import com.adobe.idp.um.api.UMException; 
import com.adobe.livecycle.usermanager.client.PreferenceManagerServiceClient;

public class ManagePreferences { 
 
    public static void main(String[] args) { 
    //Set connection properties required to invoke AEM Forms 
        Properties connectionProps = new Properties(); 
    connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "https://[server]:[port]"); 
    connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);          
    connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
    connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
    connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
     
    //Create a PreferenceManagerServiceClient object 
    ServiceClientFactory factory = ServiceClientFactory.createInstance(connectionProps); 
    PreferenceManagerServiceClient pmutil = new  PreferenceManagerServiceClient(factory); 
     
    //get the preference map for a particular node 
    String path = "/Adobe/LiveCycle/Config/UM/CommonNameOrder"; 
    Map<String, String> map; 
    try { 
        map = pmutil.getPreferences(path);                 
        for(String str:map.keySet()) { 
            //assert on the key as "ReverseOrder" 
            //assert on the value[map.get(str)] as "false" 
        }                 
    } catch (UMException e) { 
        e.printStackTrace(); 
    } 
     
    // set preferences by editing a particular key/value pair of a Node. 
    String path = "/Adobe/LiveCycle/Config/UM/CommonNameOrder"; 
    Map<String, String> map = new HashMap<String, String>(); 
    map.put("ReverseOrder", "true"); 
    try { 
        pmutil.setPreferences(path, map); 
        Map<String, String> map1 = pmutil.getPreferences(path); 
        for(String str:map1.keySet()) { 
            //assert on the key as "ReverseOrder" 
            //assert on the value[map.get(str)] as "true" 
        }     
    } catch (UMException e) { 
        e.printStackTrace(); 
    } 
} 
}
```
