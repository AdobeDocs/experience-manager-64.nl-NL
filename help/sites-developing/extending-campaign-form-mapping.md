---
title: Aangepaste formuliertoewijzingen maken
seo-title: Aangepaste formuliertoewijzingen maken
description: Wanneer u een aangepaste tabel maakt in Adobe Campaign, kunt u beter een formulier maken in AEM dat is toegewezen aan die aangepaste tabel
seo-description: Wanneer u een aangepaste tabel maakt in Adobe Campaign, kunt u beter een formulier maken in AEM dat is toegewezen aan die aangepaste tabel
uuid: f3bde513-6edb-4eb6-9048-40045ee08c4a
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: d5dac1db-2dde-4b75-a31b-e057b447f6e2
translation-type: tm+mt
source-git-commit: 8e2bd579e4c5edaaf86be36bd9d81dfffa13a573
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---


# Aangepaste formuliertoewijzingen maken{#creating-custom-form-mappings}

Wanneer u een aangepaste tabel maakt in Adobe Campaign, kunt u beter een formulier maken in AEM dat aan die aangepaste tabel wordt toegewezen.

In dit document wordt beschreven hoe u aangepaste formuliertoewijzingen kunt maken. Wanneer u de stappen in dit document voltooit, biedt u uw gebruikers een gebeurtenispagina waarop zij zich kunnen aanmelden voor een aanstaande gebeurtenis. Vervolgens volgt u deze gebruikers via Adobe Campaign.

## Vereisten {#prerequisites}

U moet het volgende installeren:

* Adobe Experience Manager
* Adobe Campaign Classic

Zie AEM [integreren met Adobe Campaign Classic](/help/sites-administering/campaignonpremise.md) voor meer informatie.

## Aangepaste formuliertoewijzingen maken {#creating-custom-form-mappings-2}

Als u aangepaste formuliertoewijzingen wilt maken, moet u de volgende stappen op hoog niveau uitvoeren. Deze worden in de volgende secties uitgebreid beschreven:

1. Een aangepaste tabel maken.
1. Breid de **zaadlijst** uit.
1. Een aangepaste toewijzing maken.
1. Maak een levering op basis van de aangepaste toewijzing.
1. Het formulier samenstellen in AEM, waarbij de gemaakte levering wordt gebruikt.
1. Verzend het formulier om het te testen.

### Aangepaste tabel maken in Adobe Campaign {#creating-the-custom-table-in-adobe-campaign}

Begin door een douanetabel in Adobe Campaign te creëren. In dit voorbeeld gebruiken we de volgende definitie om een gebeurtenistabel te maken:

```xml
<element autopk="true" label="Event" labelSingular="Event" name="event">
 <attribute label="Event Date" name="eventdate" type="date"/>
 <attribute label="Event Name" name="eventname" type="string"/>
 <attribute label="Email" name="email" type="string"/>
 <attribute label="Number of Seats" name="seats" type="long"/>
</element>
```

Nadat u de gebeurtenistabel hebt gemaakt, voert u de wizard **Databasestructuur** bijwerken uit om de tabel te maken.

### De zaadtabel uitbreiden {#extending-the-seed-table}

Tik/klik in Adobe Campaign op **Toevoegen** om een nieuwe extensie van de tabel met **zaadadressen (nms)** te maken.

![chlimage_1-194](assets/chlimage_1-194.png)

Gebruik nu de velden uit de **gebeurtenistabel** om de **zaadtabel** uit te breiden:

```xml
<element label="Event" name="custom_cus_event">
 <attribute name="eventname" template="cus:event:event/@eventname"/>
 <attribute name="eventdate" template="cus:event:event/@eventdate"/>
 <attribute name="email" template="cus:event:event/@email"/>
 <attribute name="seats" template="cus:event:event/@seats"/>
 </element>
```

Voer daarna de databasetovenaar **** Update uit om de wijzigingen toe te passen.

### Aangepaste doeltoewijzing maken {#creating-custom-target-mapping}

In **Beleid/het** Beheer van de Campagne, ga naar **Toewijzingen** van het Doel en voeg een nieuwe **Afbeelding van het Doel toe.**

>[!NOTE]
>
>Gebruik een betekenisvolle naam voor de **interne naam**.

![chlimage_1-195](assets/chlimage_1-195.png)

### Een aangepaste leveringssjabloon maken {#creating-a-custom-delivery-template}

In deze stap, voegt u een leveringsmalplaatje toe dat de gecreeerde afbeelding **van het** Doel gebruikt.

In **Middelen/Malplaatjes**, navigeer aan het Malplaatje van de Levering en dupliceer de bestaande AEM levering. Wanneer u klikt **aan**, selecteer creeer gebeurtenis **richt afbeelding**.

![chlimage_1-196](assets/chlimage_1-196.png)

### Het formulier samenstellen in AEM {#building-the-form-in-aem}

Controleer in AEM of u een Cloud Service hebt geconfigureerd in **Pagina-eigenschappen**.

Selecteer vervolgens op het tabblad **Adobe Campaign** de levering die is gemaakt bij het [maken van een aangepaste leveringssjabloon](#creating-a-custom-delivery-template).

![chlimage_1-197](assets/chlimage_1-197.png)

Wanneer u de velden configureert, moet u unieke elementnamen opgeven voor de formuliervelden.

Nadat de gebieden worden gevormd, moet u de afbeelding manueel veranderen.

Ga in CRXDE-lite naar het knooppunt **jcr:content** (van de pagina) en wijzig de **acMapping** -waarde in de interne naam van de **doeltoewijzing**.

![chlimage_1-198](assets/chlimage_1-198.png)

Controleer in de configuratie van het formulier of u het selectievakje inschakelt om te maken dat het formulier niet bestaat

![chlimage_1-199](assets/chlimage_1-199.png)

### Het formulier verzenden {#submitting-the-form}

U kunt nu het formulier verzenden en op de Adobe Campaign valideren of de waarden zijn opgeslagen.

![chlimage_1-200](assets/chlimage_1-200.png)

## Problemen oplossen {#troubleshooting}

**&quot;Ongeldig type voor waarde &#39;02/02/2015&#39; van element &#39;@eventdate&#39; (document van type &#39;Event ([adb:event])&#39;)&quot;**

Bij het verzenden van het formulier wordt deze fout aangemeld bij de AEM **error.log** .

Dit wordt veroorzaakt door een ongeldige indeling voor het datumveld. U kunt dit omzeilen door dd- **mm-jjjj** als waarde op te geven.

