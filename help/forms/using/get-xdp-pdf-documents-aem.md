---
title: XDP- en PDF-documenten ophalen in AEM Forms
seo-title: Getting XDP and PDF documents in AEM Forms
description: Met AEM Forms kunt u formulieren en ondersteunde elementen uploaden en gebruiken met adaptieve formulieren. U kunt uploadformulieren en verwante bronnen ook als een ZIP-bestand bulksgewijs verzenden.
seo-description: AEM Forms allows you to upload forms and supported assets to use with adaptive forms. You can also bulk upload forms and related resources as a ZIP.
uuid: c2a86d89-0c56-4d29-932a-dd09277fa7cb
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-manager
discoiquuid: 99da0d37-726e-42b9-b98a-5dd6c2165af6
role: Admin
exl-id: 50bf178d-7a3c-41df-9d13-99c74d944700
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%

---

# XDP- en PDF-documenten ophalen in AEM Forms {#getting-xdp-and-pdf-documents-in-aem-forms}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

U kunt uw formulieren vanuit uw lokale bestandssysteem importeren in de CRX-opslagplaats door deze te uploaden naar AEM Forms. De uploadbewerking wordt ondersteund voor de volgende elementtypen:

* Formuliersjablonen (XFA-formulieren)
* PDF forms
* Document (vlakke PDF documenten)

U kunt de ondersteunde elementtypen afzonderlijk of als ZIP-archief uploaden. U kunt een element van het type uploaden `Resource`, alleen naast een XFA-formulier in een ZIP-archief.

>[!NOTE]
>
>Zorg ervoor dat u lid bent van de `form-power-users` groep die XDP-bestanden kan uploaden. Neem contact op met de beheerder om lid te worden van de groep.

## Formulieren uploaden {#uploading-forms}

1. Meld u aan bij de gebruikersinterface van AEM Forms via `https://[server]:[port]/aem/forms.html`.
1. Navigeer naar de map waarin u het formulier of de map met formulieren wilt uploaden.
1. Tik op de werkbalk Handelingen op **Maken > Bestand uploaden**.

   ![Bestanden van lokale opslagoptie bij Maken](assets/step.png)

1. In het dialoogvenster Formulier of pakketten uploaden kunt u bladeren naar het bestand dat u wilt uploaden en het bestand kiezen. In de bestandsbrowser worden alleen de ondersteunde bestandsindelingen (ZIP, XDP en PDF) weergegeven.

   >[!NOTE]
   >
   >Een bestandsnaam mag alleen alfanumerieke tekens, afbreekstreepjes of onderstrepingstekens bevatten.

1. Klik op Uploaden na bestandsselectie om de bestanden te uploaden of klik op Annuleren om het uploaden te annuleren. Een pop-up maakt een lijst van de activa die worden toegevoegd en de activa die bij de huidige plaats worden bijgewerkt.

   >[!NOTE]
   >
   >Voor een ZIP-bestand worden de relatieve paden van alle ondersteunde elementen weergegeven. Niet-ondersteunde elementen in het ZIP-bestand worden genegeerd en niet vermeld. Als het ZIP-archief echter alleen de niet-ondersteunde elementen bevat, wordt een foutbericht weergegeven in plaats van het pop-updialoogvenster.

   ![Het dialoogvenster Uploaden tijdens het uploaden van een XFA-formulier](assets/upload-scr.png)

1. Als een of meer elementen een ongeldige bestandsnaam hebben, wordt een fout weergegeven. Corrigeer de in rood gemarkeerde bestandsnamen en upload ze opnieuw.

   ![Foutbericht bij het uploaden van een XFA-formulier](assets/upload-scr-err.png)

Wanneer het uploaden is voltooid, genereert een achtergrondworkflow miniaturen voor elk element op basis van de voorvertoning van het element. Nieuwere versies van elementen, indien geüpload, overschrijven de bestaande elementen.

### Beveiligde modus {#protected-mode}

Met AEM Forms-server kunt u JavaScript-code uitvoeren. Een kwaadaardige JavaScript-code kan schadelijk zijn voor een AEM Forms-omgeving. De beveiligde modus beperkt AEM Forms om XDP-bestanden alleen uit te voeren vanuit vertrouwde elementen en locaties. Alle XDP-gegevens die beschikbaar zijn in de gebruikersinterface van AEM Forms worden beschouwd als vertrouwde elementen.

De beveiligde modus is standaard ingeschakeld. Indien nodig kunt u de beveiligde modus uitschakelen:

1. Meld u als beheerder aan bij AEM webconsole. De URL is `https://[server]:[port]/system/console/configMgr`
1. Open Mobile Forms Configurations voor bewerking.
1. Schakel de optie Beveiligde modus uit en klik op **Opslaan**. De beveiligde modus is uitgeschakeld.

## XFA-formulieren waarnaar wordt verwezen bijwerken {#updating-referenced-xfa-forms}

In AEM Forms kan naar een XFA-formuliersjabloon worden verwezen door een adaptief formulier of een andere XFA-formuliersjabloon. Ook, kan een malplaatje naar een middel of een ander malplaatje verwijzen XFA.

Voor een adaptief formulier dat verwijst naar een XFA, zijn de velden gebonden aan de velden die beschikbaar zijn in de XFA. Bij het bijwerken van een formuliersjabloon probeert het bijbehorende adaptieve formulier te synchroniseren met de XFA. Zie voor meer informatie [Aangepaste formulieren synchroniseren met de bijbehorende XFA](/help/forms/using/synchronizing-adaptive-forms-xfa.md).

Als u een formuliersjabloon verwijdert, wordt het afhankelijke adaptieve formulier of de afhankelijke formuliersjabloon beschadigd. Een dergelijk adaptief formulier wordt soms informeel een vuile vorm genoemd. In de gebruikersinterface van AEM Forms kunt u op de volgende twee manieren de vuile formulieren vinden.

* Er wordt een waarschuwingspictogram weergegeven op de miniatuur van het aangepaste formulier in de lijst met elementen. Het volgende bericht wordt weergegeven wanneer u de aanwijzer boven het waarschuwingspictogram houdt.

   `Schema/Form Template for this adaptive form has been updated so please go to Authoring mode and rebase it with new version.`

![Waarschuwing voor een adaptief formulier dat niet gesynchroniseerd is na het bijwerken van de bijbehorende XFA](assets/dirtyaf.png)

Er wordt een vlag onderhouden om aan te geven of een adaptief formulier bevuild is. Deze informatie is beschikbaar op de pagina met formuliereigenschappen, naast de metagegevens van het formulier. Alleen voor vuile adaptieve formulieren, een eigenschap metadata `Model Refresh` displays `Recommended` waarde.

![Indicatie van een adaptief formulier dat niet synchroon is met het XFA-model](assets/model-refresh.png)
