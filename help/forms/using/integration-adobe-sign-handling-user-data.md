---
title: Integratie met Adobe Sign | Gebruikersgegevens verwerken
seo-title: Integratie met Adobe Sign | Gebruikersgegevens verwerken
description: 'null'
seo-description: 'null'
uuid: cb3a455d-2e33-44c8-8f71-3a7ecd939cd8
topic-tags: grdp
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: e9e0d8fb-955e-4021-9e9a-9c95c6ffe88d
translation-type: tm+mt
source-git-commit: 13d364ec820b48fb8b80da2ffd30faeeb7813a28
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---


# Integratie met Adobe Sign | Gebruikersgegevens {#integration-with-adobe-sign-handling-user-data} verwerken

AEM Forms kan met Adobe Sign worden geïntegreerd om workflows voor e-handtekeningen mogelijk te maken in adaptieve formulieren voor het verwerken van formulieren of overeenkomsten voor juridische, verkoop-, loon- en personeelsbeheerworkflows. Het staat voor enig en multiuser het ondertekenen, opeenvolgende en gelijktijdige het ondertekenen werkschema&#39;s toe, het ondertekenen van formulieren als anonieme of het programma geopende gebruiker, en veelvoudige manieren om gebruikers voor authentiek te verklaren.

Wanneer een ondertekenaar of meerdere ondertekenaars een adaptief formulier ondertekenen en verzenden, wordt een Adobe Sign-overeenkomst gegenereerd die informatie over de ondertekenaars bevat.

Zie [Adobe Sign in een adaptieve vorm gebruiken](/help/forms/using/working-with-adobe-sign.md) voor meer informatie over de integratie van AEM Forms met Adobe Sign.

## Gebruikersgegevens en gegevensopslag {#data}

Het adaptieve formulier dat geschikt is voor Adobe Sign, bevat informatie over de ondertekenaars en kan andere gebruikersgegevens bevatten die door het adaptieve formulier zijn verzameld. De Adobe Sign-service slaat gebruikersgegevens op met de handtekening in de overeenkomst. De overeenkomst wordt opgeslagen op een Adobe Sign-server die is geconfigureerd in AEM Forms-cloudservices. Als het adaptieve formulier is geconfigureerd om de verzendactie Forms Portal te gebruiken, worden de gegevens van de overeenkomst samen met de formuliergegevens opgeslagen in de gegevensopslag van de portal Formulieren.

## Gebruikersgegevens openen en verwijderen {#access-and-delete-user-data}

Gebruikersgegevens worden verzameld binnen de overeenkomst, maar niet opgeslagen in een van de servicetabellen. Met Adobe Sign kunnen beheerders hun eigen keuzes maken voor het beheer van gegevens die ze in de service beheren. Privacybeheerders van de Adobe Sign-service kunnen op basis van het e-mailadres van een aanvrager overeenkomsten weergeven of verwijderen.

Adobe Sign biedt een webtoepassing waarmee deelnemers kunnen zoeken naar overeenkomsten en deze zo nodig kunnen verwijderen. Zie [Adobe Sign - Functie voor meer informatie: Gebruikersgegevens verwijderen](https://helpx.adobe.com/sign/help/adobesign_gdpr_user_deletion.html).

Overeenkomstgegevens voor adaptieve formulieren die zijn geconfigureerd om de handeling voor het verzenden van het Forms Portal te gebruiken, worden ook opgeslagen in de gegevensopslag van het formulierportaal. Zie [Forms portal voor toegang tot gegevens en verwijdering uit de opslag met formulierportalgegevens | Gebruikersgegevens verwerken](/help/forms/using/forms-portal-handling-user-data.md).
