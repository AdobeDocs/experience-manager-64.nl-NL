---
title: PUBLICEER geen gebruikersinterface op basis van rollen in Correspondentenbeheer
seo-title: PUBLICEER geen gebruikersinterface op basis van rollen in Correspondentenbeheer
description: 'null'
seo-description: 'null'
page-status-flag: de-activated
uuid: 60808852-f63f-4c0a-badb-b0af93c995a8
contentOwner: gtalwar
products: SG_EXPERIENCEMANAGER/6.3/FORMS
discoiquuid: 342f111e-f15a-4f9a-8993-f90760363c02
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---


# PUBLICEER geen gebruikersinterface op basis van rollen in Correspondentenbeheer {#do-not-publish-role-based-user-interface-in-correspondence-management}

In AEM kan Admin op rol-gebaseerde toegang tot verschillende gebruikersgroepen verlenen die diverse acties op verschillende middelen uitvoeren. De functie voor het maken of bewerken van gegevenswoordenboeken kan bijvoorbeeld alleen beschikbaar zijn voor gebruikers in een specifieke gebruikersgroep, terwijl andere gebruikers de gegevenswoordenboeken alleen kunnen weergeven en gebruiken.

In de AEM-interface worden de opties weergegeven, zoals het maken of bewerken van een elementtype op basis van het toegangsniveau van de gebruiker. Als een gebruiker bijvoorbeeld niet over de machtigingen beschikt om een gegevenswoordenboek te maken, wordt de optie voor het maken van een gegevenswoordenboek niet weergegeven in de gebruikersinterface.

Hoewel CRX u toestaat om de toegangsrechten voor zowel gebruiker als groepsrekeningen te vormen, is dit artikel over rol of gebruikersgroep gebaseerde toegangsrechten.

Voor meer informatie over groepen, toestemmingen, toegangsbeheerlijsten, en het beheren van gebruikers en groepen, zie [Gebruikersbeheer en Veiligheid](/help/sites-administering/security.md).

## Machtigingen {#managing-permissions} beheren

1. Zorg ervoor dat de gebruiker waarvoor u de machtigingen wilt beheren, wordt toegevoegd aan de relevante gebruikersgroep.

   De gebruiker Jan Smit wordt bijvoorbeeld toegevoegd aan de groepen `agents` en `cm-creditcard`. Zie Gebruikers of groepen toevoegen aan een groep voor meer informatie. Zie [Gebruikers en gebruikersgroepen beheren](/help/communities/users.md) voor meer informatie.

   ![]()

1. Maak de mappen die geschikt zijn voor het toestaan van de bedoelde machtigingen.

   Als een onderneming bijvoorbeeld hypotheek op huis, creditcard of verzekeringsdivisies heeft, kunnen zij mappen maken met de namen `HomeMortgage`, `CreditCard,`en `Insurance` om de relevante activa te behouden en op selectieve wijze toegang te verlenen aan agenten voor activa die alleen relevant zijn voor hun afdelingen.

1. Voer een van de volgende handelingen uit om toegang te krijgen tot AEM WCM-beveiliging:

   1. Klik in het welkomstscherm of op verschillende locaties in AEM op het beveiligingspictogram:

   1. Navigeer rechtstreeks naar `https://[server]:[port]/useradmin`. Zorg ervoor dat u zich als beheerder aanmeldt bij AEM.

      ![]()
   In de linkerstructuur worden alle gebruikers en groepen weergegeven die zich momenteel in het systeem bevinden. U kunt de kolommen selecteren die u wilt weergeven, de inhoud van de kolommen sorteren en zelfs de volgorde wijzigen waarin de kolommen worden weergegeven door de kolomkop naar een nieuwe positie te slepen.

   De tabbladen bieden toegang tot verschillende configuraties:

1. Tik in de linkerstructuurlijst op de naam van de desbetreffende groep en selecteer vervolgens het tabblad Machtigingen.

   Als u de naam van de groep wilt zoeken, typt u de naam van de groep in de beschikbare ruimte.

1. Navigeer op het tabblad Machtigingen naar het pad waaraan u machtigingen wilt toevoegen. De mappen voor Correspondentiebeheer bevinden zich in de map `content/apps/cm/`.

   Schakel het selectievakje in de kolom Lid in voor de leden die u machtigingen voor dat pad wilt hebben. Schakel het selectievakje voor het lid waarvoor u machtigingen wilt verwijderen uit. In de cel waarin u wijzigingen hebt aangebracht, wordt een rood driehoekje weergegeven.

   ![useradmin-creditcard](assets/useradmin-creditcard.png)

   >[!NOTE]
   >
   >De machtigingen die in een map zijn opgegeven, hebben voorrang op de machtigingen die in de submappen zijn opgegeven.

1. Tik op Opslaan.
1. Staptekst
1. Staptekst
1. Staptekst

