---
title: Integratie met Acrobat Sign | Gebruikersgegevens verwerken
seo-title: Integration with Acrobat Sign | Handling user data
description: AEM Forms kan met Acrobat Sign worden geïntegreerd om workflows voor e-handtekeningen mogelijk te maken in adaptieve formulieren voor het verwerken van formulieren of overeenkomsten voor juridische, verkoop-, loon- en personeelsbeheerworkflows. Dig dieper op gebruikersgegevens, gegevensopslag, en toegang en schrapt gebruikersgegevens.
seo-description: AEM Forms integrates with Acrobat Sign to enable e-signature workflows in adaptive forms to process forms or agreements for legal, sales, payroll, human resource management workflows. Dig deeper on user data, data stores, and access and delete user data.
uuid: cb3a455d-2e33-44c8-8f71-3a7ecd939cd8
topic-tags: grdp
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: e9e0d8fb-955e-4021-9e9a-9c95c6ffe88d
feature: Acrobat Sign
role: Admin
exl-id: c2061de7-8627-4595-b96c-aa2d6abffddd
source-git-commit: f8b19b6723d333e76fed111b9fde376b3bb13a1d
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 0%

---

# Integratie met Acrobat Sign | Gebruikersgegevens verwerken {#integration-with-adobe-sign-handling-user-data}

AEM Forms kan met Acrobat Sign worden geïntegreerd om workflows voor e-handtekeningen mogelijk te maken in adaptieve formulieren voor het verwerken van formulieren of overeenkomsten voor juridische, verkoop-, loon- en personeelsbeheerworkflows. Het staat voor enig en multiuser het ondertekenen, opeenvolgende en gelijktijdige het ondertekenen werkschema&#39;s toe, het ondertekenen van formulieren als anonieme of het programma geopende gebruiker, en veelvoudige manieren om gebruikers voor authentiek te verklaren.

Wanneer een ondertekenaar of meerdere ondertekenaars een adaptief formulier ondertekenen en verzenden, wordt een Acrobat Sign-overeenkomst gegenereerd die informatie over de ondertekenaars bevat.

Ga voor meer informatie over de integratie van AEM Forms met Acrobat Sign naar [Acrobat Sign in een adaptieve vorm gebruiken](/help/forms/using/working-with-adobe-sign.md).

## Gebruikersgegevens en gegevensopslag {#data}

Het adaptieve formulier dat geschikt is voor Acrobat Sign, bevat informatie over de ondertekenaars en kan andere gebruikersgegevens bevatten die door het adaptieve formulier zijn verzameld. De Acrobat Sign-service slaat gebruikersgegevens op met de handtekening in de overeenkomst. De overeenkomst wordt opgeslagen op een Acrobat Sign-server die is geconfigureerd in AEM Forms-cloudservices. Als het adaptieve formulier is geconfigureerd om de verzendactie Forms Portal te gebruiken, worden de gegevens van de overeenkomst samen met de formuliergegevens opgeslagen in de gegevensopslag van de portal Formulieren.

## Gebruikersgegevens openen en verwijderen {#access-and-delete-user-data}

Gebruikersgegevens worden verzameld binnen de overeenkomst, maar niet opgeslagen in een van de servicetabellen. Met Acrobat Sign kunnen beheerders hun eigen keuzes maken voor het beheer van gegevens die ze in de service beheren. Privacybeheerders van de Acrobat Sign-service kunnen op basis van het e-mailadres van een aanvrager overeenkomsten weergeven of verwijderen.

Acrobat Sign biedt een webtoepassing waarmee deelnemers kunnen zoeken naar overeenkomsten en deze zo nodig kunnen verwijderen. Zie voor meer informatie [Acrobat Sign - Functie: Gebruikersgegevens verwijderen](https://helpx.adobe.com/sign/help/adobesign_gdpr_user_deletion.html).

Overeenkomstgegevens voor adaptieve formulieren die zijn geconfigureerd om de handeling voor het verzenden van het Forms Portal te gebruiken, worden ook opgeslagen in de gegevensopslag van het formulierportaal. Als u gegevens uit de gegevensopslag van het formulierportal wilt openen en verwijderen, raadpleegt u [Forms Portal | Gebruikersgegevens verwerken](/help/forms/using/forms-portal-handling-user-data.md).
