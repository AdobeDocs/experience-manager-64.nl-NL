---
title: Desktop-app AEM voor AEM Forms
seo-title: AEM desktop app for AEM Forms
description: Met AEM bureaubladtoepassing kunt u de gegevensopslagruimte van Adobe Experience Manager (AEM) en de binaire bestanden van AEM Forms toewijzen aan een netwerkmap op uw systeem. Meer informatie over de middelen die worden ondersteund in AEM bureaubladtoepassing en over het inschakelen van AEM Forms voor AEM bureaubladtoepassing.
seo-description: AEM desktop app lets you map the Adobe Experience Manager (AEM) Assets repository and AEM Forms binary files to a network directory on your system. Learn more about the assets supported in AEM desktop app and how to enable AEM Forms for AEM desktop app.
uuid: 99e0f2fb-8623-45bb-8e2e-5c5d6f482366
contentOwner: khsingh
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: manage
discoiquuid: c30332b6-e012-442d-8e84-28832c116c7b
noindex: true
role: Admin
exl-id: 26cd0851-cadf-4a8f-b3bf-59f77671f584
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# Desktop-app AEM voor AEM Forms {#aem-desktop-app-for-aem-forms}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met AEM bureaubladtoepassing kunt u de gegevensopslagruimte van Adobe Experience Manager (AEM) en de binaire bestanden van AEM Forms toewijzen aan een netwerkmap op uw systeem. U kunt de gesynchroniseerde elementen en binaire bestanden weergeven in een bestandsverkenner en verschillende apps gebruiken om de bestanden naar wens te bewerken. Behalve het bekijken van de bestanden kunt u ook binaire bestanden maken, uploaden en verwijderen. U kunt bestanden ook rechtstreeks vanuit de software openen, bewerken en opslaan. U kunt bijvoorbeeld een XDP-bestand rechtstreeks vanuit Designer openen en bewerken. De wijzigingen die u lokaal aanbrengt in de elementen worden weerspiegeld in de AEM Assets-opslagplaats en de gebruikersinterface van AEM Forms.

U kunt de app downloaden van een AEM. Ga voor gedetailleerde informatie over het downloaden van de app naar [Opmerkingen bij de release AEM bureaubladtoepassing](https://helpx.adobe.com/experience-manager/desktop-app/release-notes.html).

## AEM Forms-middelen die worden ondersteund in AEM bureaubladtoepassing {#aem-forms-assets-supported-in-aem-desktop-app}

Met de app kunt u binaire bestanden van het type AEM Forms synchroniseren met het type Form Templates (.xdp), PDF Form (.pdf), Document (.pdf), Images, XML-schema (.xsd), stijlpagina&#39;s (.xfs). In de app worden alle andere bestanden (niet-ondersteunde bestanden) weergegeven als bestanden van 0 byte. Door niet-ondersteunde bestanden als 0-byte bestanden te vermelden, weet de gebruiker zeker dat er andere middelen op de AEM Forms-server beschikbaar zijn.

>[!NOTE]
>
>Een bestandsnaam mag alleen alfanumerieke tekens, afbreekstreepjes of onderstrepingstekens bevatten.

## AEM Forms inschakelen voor AEM bureaubladtoepassing {#enable-aem-forms-for-aem-desktop-app}

AEM desktop app gebruikt WebDAV-protocol op Microsoft Windows en SMB1 op Mac OS X om verbinding te maken met een AEM Forms-server. AEM Forms-server is niet in staat om binaire bestanden en andere elementen te synchroniseren met een WebDAV- of SMB-client. Voer de volgende stappen uit om AEM Forms voor AEM desktop app in te schakelen:

1. Meld u als beheerder aan bij AEM Forms.
1. Klik in de auteurinstantie op ![adobeexperienceManager](assets/adobeexperiencemanager.png) **[!UICONTROL Adobe Experience Manager > Tools]** ![hamer](assets/hammer.png) **[!UICONTROL > Deployment > Operations > Web Console]**. De webconsole wordt in een nieuw venster geopend.
1. Zoek in het venster Webconsole de **[!UICONTROL FormsManager AddOn Configuration]** optie.
1. Schakel in het dialoogvenster FormsManager AddOn-configuratie de optie **[!UICONTROL Asynchronously Sync Resources]** en klik op **[!UICONTROL Save]**.
1. Start de AEM Forms-server opnieuw. Nadat u de computer opnieuw hebt opgestart, kan de AEM Forms-server inhoud accepteren en delen met AEM bureaubladtoepassing.
1. Open de toepassing en maak verbinding met de AEM Forms-server.

   Wanneer de verbinding is gelukt, vult de toepassing de `content/dam` en `content/dam/formsanddocuments` mappen. U kunt de app gebruiken om bestanden van de bovenliggende mappen naar lokale mappen te verplaatsen en omgekeerd, en om inhoud tussen automatisch gevulde mappen te verplaatsen.
