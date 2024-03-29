---
title: Programmatoegang tot het AEM JCR
seo-title: How to programmatically access the AEM JCR
description: U kunt via programmacode knooppunten en eigenschappen wijzigen die zich bevinden in de AEM opslagplaats, die deel uitmaakt van de Adobe Marketing Cloud
seo-description: You can programmatically modify nodes and properties located within the AEM repository, which is part of the Adobe Marketing Cloud
uuid: 2051d03f-430a-4cae-8f6d-e5bc727d733f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 69f62a38-7991-4009-8db7-ee8fd35dc535
exl-id: f2317fd5-df64-4042-b17e-0e0506161b90
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Programmatoegang tot het AEM JCR{#how-to-programmatically-access-the-aem-jcr}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt via programmacode knooppunten en eigenschappen wijzigen in de Adobe CQ-opslagplaats, die deel uitmaakt van de Adobe Marketing Cloud. Als u toegang wilt krijgen tot de CQ-opslagplaats, gebruikt u de JCR-API (Java Content Repository). U kunt de Java JCR API gebruiken om (CRUD)-bewerkingen te maken, te vervangen, bij te werken en te verwijderen op inhoud in de Adobe CQ-opslagplaats. Voor meer informatie over de Java JCR API raadpleegt u [https://jackrabbit.apache.org/jcr/jcr-api.html](https://jackrabbit.apache.org/jcr/jcr-api.html).

>[!NOTE]
>
>Dit ontwikkelingsartikel wijzigt het JCR van Adobe CQ van een externe toepassing van Java. U kunt het JCR daarentegen wijzigen vanuit een OSGi-bundel met behulp van de JCR API. Zie voor meer informatie [CQ-gegevens behouden in de Java Content Repository](https://helpx.adobe.com/experience-manager/using/persisting-cq-data-java-content1.html).

>[!NOTE]
>
>Als u de JCR API wilt gebruiken, voegt u de `jackrabbit-standalone-2.4.0.jar` bestand naar het klassepad van uw Java-toepassing. U kunt dit JAR-bestand verkrijgen via de Java JCR API-webpagina op [https://jackrabbit.apache.org/jcr/jcr-api.html](https://jackrabbit.apache.org/jcr/jcr-api.html).

>[!NOTE]
>
>Ga voor meer informatie over het zoeken naar de Adobe CQ JCR met de JCR Query API [Adobe Experience Manager-gegevens opvragen met de JCR API](https://helpx.adobe.com/experience-manager/using/querying-experience-manager-data-using1.html).

## Een instantie Repository maken {#create-a-repository-instance}

Hoewel er verschillende manieren zijn om verbinding te maken met een opslagplaats en een verbinding tot stand te brengen, gebruikt dit ontwikkelingsartikel een statische methode die tot de `org.apache.jackrabbit.commons.JcrUtils` klasse. De naam van de methode is `getRepository`. Deze methode gebruikt een tekenreeksparameter die de URL van de Adobe CQ-server vertegenwoordigt. Bijvoorbeeld `http://localhost:4503/crx/server`.

De `getRepository`methode retourneert een `Repository`-instantie, zoals in het volgende codevoorbeeld wordt getoond.

```java
//Create a connection to the AEM JCR repository running on local host
Repository repository = JcrUtils.getRepository("http://localhost:4503/crx/server");
```

## Een instantie Sessie maken {#create-a-session-instance}

De `Repository`-instantie staat voor de CRX-opslagplaats. U gebruikt de `Repository`-instantie om een sessie met de gegevensopslagruimte tot stand te brengen. Als u een sessie wilt maken, roept u de opdracht `Repository`van `login`methode en een `javax.jcr.SimpleCredentials` object. De `login`methode retourneert een `javax.jcr.Session` -instantie.

U maakt een `SimpleCredentials`object door de constructor ervan te gebruiken en de volgende tekenreekswaarden door te geven:

* de gebruikersnaam;
* Het bijbehorende wachtwoord

Roep bij het doorgeven van de tweede parameter het object String `toCharArray`methode. De volgende code laat zien hoe u de `login`methode die een `javax.jcr.Sessioninstance`.

```java
//Create a Session instance
javax.jcr.Session session = repository.login( new SimpleCredentials("admin", "admin".toCharArray()));
```

## Een Node-instantie maken {#create-a-node-instance}

Een `Session`instantie om een `javax.jcr.Node` -instantie. A `Node`Met instantie kunt u knooppuntbewerkingen uitvoeren. U kunt bijvoorbeeld een nieuw knooppunt maken. Als u een knooppunt wilt maken dat het hoofdknooppunt vertegenwoordigt, roept u het `Session`instantie `getRootNode` , zoals in de volgende coderegel wordt getoond.

```java
//Create a Node
Node root = session.getRootNode();
```

Wanneer u een `Node`kunt u taken uitvoeren, zoals het maken van een ander knooppunt en het toevoegen van een waarde aan dat knooppunt. Met de volgende code worden bijvoorbeeld twee knooppunten gemaakt en een waarde toegevoegd aan het tweede knooppunt.

```java
// Store content 
Node day = adobe.addNode("day");
day.setProperty("message", "Adobe CQ is part of the Adobe Digital Marketing Suite!");
```

## Nodewaarden ophalen {#retrieve-node-values}

Om een knoop en zijn waarde terug te winnen, haal `Node`van `getNode`methode en geef een koordwaarde door die volledig-gekwalificeerde weg aan de knoop vertegenwoordigt. Overweeg de knoopstructuur die in het vorige codevoorbeeld wordt gecreeerd. Als u het dagknooppunt wilt ophalen, geeft u adobe/day op, zoals in de volgende code wordt getoond:

```java
// Retrieve content
Node node = root.getNode("adobe/day");
System.out.println(node.getPath());
System.out.println(node.getProperty("message").getString());
```

## Maak knooppunten in de Adobe CQ Repository {#create-nodes-in-the-adobe-cq-repository}

In het volgende Java-codevoorbeeld wordt een Java-klasse voorgesteld die verbinding maakt met Adobe CQ. `Session`en voegt nieuwe knooppunten toe. Een knoop wordt toegewezen een gegevenswaarde en dan wordt de waarde van de knoop en zijn weg geschreven aan de console. Als u klaar bent met de sessie, moet u zich afmelden.

```java
/*
 * This Java Quick Start uses the jackrabbit-standalone-2.4.0.jar
 * file. See the previous section for the location of this JAR file
 */
 
import javax.jcr.Repository; 
import javax.jcr.Session; 
import javax.jcr.SimpleCredentials; 
import javax.jcr.Node; 
 
import org.apache.jackrabbit.commons.JcrUtils;
import org.apache.jackrabbit.core.TransientRepository;

public class GetRepository {

public static void main(String[] args) throws Exception { 
 
try { 
 
    //Create a connection to the CQ repository running on local host 
    Repository repository = JcrUtils.getRepository("http://localhost:4503/crx/server");
   
   //Create a Session
   javax.jcr.Session session = repository.login( new SimpleCredentials("admin", "admin".toCharArray())); 
 
  //Create a node that represents the root node
  Node root = session.getRootNode(); 
 
  // Store content 
  Node adobe = root.addNode("adobe"); 
  Node day = adobe.addNode("day"); 
  day.setProperty("message", "Adobe CQ is part of the Adobe Digital Marketing Suite!");

  // Retrieve content 
  Node node = root.getNode("adobe/day"); 
  System.out.println(node.getPath()); 
  System.out.println(node.getProperty("message").getString()); 
 
  // Save the session changes and log out
  session.save(); 
  session.logout();
  }
 catch(Exception e){
  e.printStackTrace();
  }
 } 
}
```

Nadat u het volledige codevoorbeeld in werking stelt en de knopen creeert, kunt u de nieuwe knopen in bekijken **[!UICONTROL CRXDE Lite]**, zoals in de volgende afbeelding wordt getoond.

![chlimage_1-68](assets/chlimage_1-68.png)
