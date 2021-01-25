---
title: Maven gebruiken voor Gemeenschappen
seo-title: Maven gebruiken voor Gemeenschappen
description: AEM Communities API-jar en AEM Uber API-jar
seo-description: AEM Communities API-jar en AEM Uber API-jar
uuid: ea37a89a-db6c-4018-8ab9-f5717e6c0421
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: a726c904-aadd-4678-be84-9e05808ab8be
translation-type: tm+mt
source-git-commit: 5affffac6f953bcf1d436d8492ad6dd2a041b3b4
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---


# Maven gebruiken voor Gemeenschappen {#using-maven-for-communities}

## Overzicht {#overview}

Deze sectie van de documentatie van AEM Communities is naast:

* [Bouwen AEM projecten met Apache Maven](../../help/sites-developing/ht-projects-maven.md).

Er is slechts één &quot;uber&quot;artefact dat individuele artefacten vervangt:

* AEM [Uber API jar](../../help/sites-developing/ht-projects-maven.md#what-is-the-uberjar)

>[!NOTE]
>
>Vanaf AEM 6.4 worden de communautaire API&#39;s niet expliciet vrijgegeven. Alle Community API&#39;s zijn nu opgenomen in de Uber jar zelf.
>
>Aanbevolen wordt de meest recente versie van de Gemeenschappen bij te houden.
>
>Zie [Laatste releases](deploy-communities.md#latest-releases) sectie om de meest recente versie te identificeren.

## Voorbeeld van een weven afhankelijkheid {#maven-dependency-example}

```xml
<dependency>
    <groupId>com.adobe.aem</groupId>
    <artifactId>uber-jar</artifactId>
    <version>6.4.8.3</version>
    <scope>provided</scope>
</dependency>
```

>[!NOTE]
>
>Zie [AEM Uber jar repository](https://mvnrepository.com/artifact/com.adobe.aem/uber-jar) om het nieuwste Uber jar artefact te identificeren.

<!--
# Using Maven for Communities {#using-maven-for-communities}

## Overview {#overview}

This section of the AEM Communities documentation is in addition to:

* [How to Build AEM Projects using Apache Maven](../../help/sites-developing/ht-projects-maven.md)

There are now two "uber" artifacts that replace individual artifacts:

* AEM [Communities API jar](#communities-api-jar-artifact)
* AEM [Uber API jar](../../help/sites-developing/ht-projects-maven.md#what-is-the-uberjar)

## Communities API Jar Artifact {#communities-api-jar-artifact}

Following is an example of a GAV for the AEM Communities API jar:

```xml
<dependency>
    <groupId>com.adobe.cq.social</groupId>
    <artifactId>cq-socialcommunities-api</artifactId>
    <version>1.11.170</version>
    <scope>provided</scope>
</dependency>

```

Ensure thet the version specified corresponds with the Communities package version installed for AEM Communities. To verify the installed version number:

1. Login with adminstrative privileges.
2. Browse to [Package Manager](../../help/sites-administering/package-manager.md). For example, [http://localhost:4502/crx/packmgr/](http://localhost:4502/crx/packmgr/)

3. locate the package *cq-socialcommunities-pkg-1.x.xxx*
4. extract the version from the package name
    * first version for AEM 6.3 is version 1.11.170
    * feature packs will be versions 1.12.xxx
    
>[!NOTE]
>
>It is recommended to keep up-to-date with the most recent Communities release.
>
>Visit the [Latest Releases](deploy-communities.md#latest-releases) section to identify the most recent version.

## Maven Dependency Example {#maven-dependency-example}

The Communities API jar must be specified before the Uber API jar.

```xml
<dependency>
    <groupId>com.adobe.cq.social</groupId>
    <artifactId>cq-socialcommunities-api</artifactId>
    <version>1.11.170</version>
    <scope>provided</scope>
</dependency>
<dependency>
    <groupId>com.adobe.aem</groupId>
    <artifactId>uber-jar</artifactId>
    <version>6.3.0</version>
    <scope>provided</scope>
    <classifier>apis</classifier>
</dependency>
```
-->