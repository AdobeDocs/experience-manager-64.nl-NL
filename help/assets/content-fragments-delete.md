---
title: Contentfragmenten - Overwegingen verwijderen
seo-title: Contentfragmenten - Overwegingen verwijderen
description: Contentfragmenten - Overwegingen verwijderen
seo-description: Contentfragmenten - Overwegingen verwijderen
uuid: b4161a0e-7e17-4547-9bdd-cf3b1d0d7d63
contentOwner: aheimoz
topic-tags: content-fragments
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: eaf65bdd-9091-4985-90bd-5eb2148965e3
translation-type: tm+mt
source-git-commit: 3fa80e73fb6e9400fbeba29d80aa57e080b6f333
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 12%

---


# Contentfragmenten - Overwegingen verwijderen {#content-fragments-delete-considerations}

>[!CAUTION]
>
>Voor sommige functies van Content Fragment is de toepassing van [AEM 6.4 Service Pack 2 (6.4.2.0) of hoger](/help/release-notes/sp-release-notes.md)vereist.

## Machtigingen - Verwijderen of Niet verwijderen {#permissions-delete-or-not-delete}

De capaciteit om inhoud te schrappen is krachtig, maar potentieel gevoelig, met vele industrieën die moeten beperken en controleren hoe deze voorrechten worden verdeeld.

Met betrekking tot het schrappen van toestemmingen, moeten de Fragmenten van de Inhoud op twee niveaus worden overwogen:

1. **Het inhoudsfragment als één entiteit.**

   * **Hoofdlettergebruik**: Een gebruiker die een inhoudsfragment moet bewerken/bijwerken - **en een volledig fragment** moet verwijderen.
   * **Machtigingen**: De machtiging [Verwijderen](/help/sites-administering/security.md#actions) kan worden [toegewezen via Gebruiker en/of Groepsbeheer](/help/sites-administering/security.md#managing-permissions).

1. **De meerdere subentiteiten waaruit een inhoudsfragment bestaat; bijvoorbeeld variaties, subknooppunten.**

   De basiswerking van de inhoudfragment-editor vereist dat dergelijke tijdelijke subelementen kunnen worden verwijderd. Bijvoorbeeld bij het manipuleren van variaties; ook bij het bewerken van metagegevens of het beheren van bijbehorende inhoud.

   * **Hoofdlettergebruik**: Een gebruiker die een inhoudsfragment moet bewerken/bijwerken - **zonder dat het is toegestaan een volledig fragment** te verwijderen.
   * **Machtigingen**: Zie [Machtigingen vereist voor alleen](content-fragments-delete.md#permissions-required-for-editor-functionality-only)bewerkingsfunctionaliteit.

>[!NOTE]
>
>When a user does not have any [Delete](/help/sites-administering/security.md#actions) permissions, the Content Fragment editor operates in *read-only* mode.

>[!NOTE]
>
>Zie ook [hoe te de Verrichtingen van het Beheer van de Gebruiker in AEM](/help/sites-administering/audit-user-management-operations.md)controleren.

## Machtigingen alleen vereist voor Editor-functionaliteit {#permissions-required-for-editor-functionality-only}

Voor gebruikers die een contentfragment moeten bewerken of bijwerken, **zonder hun toe te staan om een volledig fragment te verwijderen**, moeten specifieke machtigingen worden toegewezen, aangezien de basisbewerking van de contentfragmenteditor vereist dat tijdelijke subelementen kunnen worden verwijderd.

Bijvoorbeeld bij het manipuleren van variaties; ook bij het bewerken van metagegevens of het beheren van bijbehorende inhoud.

>[!NOTE]
>
>De machtigingen voor verwijderen die vereist zijn om een inhoudsfragment te bewerken/bij te werken, worden opgenomen in de machtiging Verwijderen die is [toegewezen via Gebruiker en/of Groepsbeheer](/help/sites-administering/security.md#managing-permissions).

De machtigingen die nodig zijn om een fragment te bewerken/bij te werken, moeten worden toegepast op het knooppunt met het inhoudsfragment of op een geschikt bovenliggend knooppunt (op elk niveau onder `/content/dam`). Wanneer toegewezen aan een dergelijk bovenliggend knooppunt, worden de machtigingen toegepast op alle knooppunten in die vertakking.

Bijvoorbeeld een map die alle inhoudsfragmenten bevat, zoals:

* `/content/dam/contentfragments`

>[!CAUTION]
>
>Het instellen van de machtigingen voor `/content/dam` is ook mogelijk, aangezien alle inhoudsfragmenten hier worden opgeslagen.
>
>Deze handeling past echter dezelfde verwijdermachtigingen ook toe op *alle* andere elementtypen.

U kunt een inhoudsfragment alleen bewerken/bijwerken als een specifieke gebruiker en/of groep de volgende machtigingen heeft:

>[!NOTE]
>
>In deze lijst worden alle vereiste rechten weergegeven, niet alleen de verwijderingsrechten.

* Voor de knooppunten of mappen van het inhoudsfragment:

   * `jcr:addChildNodes`, `jcr:modifyProperties`

* Voor het `jcr:content` knooppunt van alle inhoudsfragmenten:

   * `jcr:addChildNodes`, `jcr:modifyProperties` en `jcr:removeChildNodes`

* Voor alle knooppunten onder `jcr:content` alle inhoudsfragmenten:

   * `jcr:addChildNodes`, `jcr:modifyProperties` en `jcr:removeChildNodes`, `jcr:removeNode`

Deze `remove` voorrechten moeten worden [beheerd gebruikend de Lijsten van het Toegangsbeheer, binnen CRXDE Lite](/help/sites-administering/user-group-ac-admin.md#access-right-management).

De `add` en de `modify` voorrechten kunnen ook in CRXDE Lite, of het gebruiken van de console van het Beheer van de Gebruiker worden beheerd.

Bijvoorbeeld, de definitie van de `remove` voorrechten voor een groep `content-authors-no-delete`:

![cf-delete-03](assets/cf-delete-03.png)

