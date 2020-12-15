---
title: AEM 3D integreren met Autodesk Maya
seo-title: AEM 3D integreren met Autodesk Maya
description: U kunt desgewenst AEM 3D integreren met Autodesk® Maya®-software om ondersteuning voor systeemeigen Maya-bestanden (.MA en .MB) in te schakelen en om 3D-assets te kunnen renderen in AEM met elke beschikbare Maya-renderer.
seo-description: U kunt desgewenst AEM 3D integreren met Autodesk® Maya®-software om ondersteuning voor systeemeigen Maya-bestanden (.MA en .MB) in te schakelen en om 3D-assets te kunnen renderen in AEM met elke beschikbare Maya-renderer.
uuid: 07ff17b6-bdfc-4617-8b16-42aaf5c73fc7
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 3d063268-17d7-4db6-8028-682537645377
translation-type: tm+mt
source-git-commit: b698a1348df3ec2ab455c236422784d10cbcf7c2
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 0%

---


# AEM 3D integreren met Autodesk Maya {#integrating-aem-d-with-autodesk-maya}

>[!NOTE]
>
>Deze taak is optioneel en heeft alleen betrekking op Windows.

U kunt desgewenst AEM 3D integreren met Autodesk® Maya®-software om ondersteuning voor systeemeigen Maya-bestanden (`.MA` en `.MB`) in te schakelen en om 3D-elementen te laten renderen in AEM met elke beschikbare Maya-renderer.

*Deze integratie geldt alleen* voor Windows.

Wanneer u integreert met Autodesk Maya, moet u Autodesk Maya installeren en configureren, het pad naar de uitvoerbare map van Maya toevoegen, Maya inschakelen voor inname en renderen en de integratie testen.

Zie [Geavanceerde configuratie-instellingen](advanced-config-3d.md).

Zie ook [AEM 3D integreren met AutoDesk 3ds Max](integrating-aem-3d-with-autodesk-3ds-max.md).

**AEM 3D integreren met Autodesk Maya**:

1. Installeer Autodesk Maya 2016-software op dezelfde servers als AEM.

   Controleer na de installatie of u Maya kunt openen en gebruiken en of er geen licentieproblemen zijn.

   >[!NOTE]
   >
   >AEM gebruikt alleen het rendergereedschap Maya-opdrachtregel (`render.exe`). Met één Maya-netwerklicentie kunnen maximaal vijf servers tegelijk Maya-inhoud verwerken of renderen.

1. Schakel in Maya de Autodesk FBX®-plug-in in.
1. Installeer de insteekmodule voor het renderen van MentalRay of een andere gewenste renderer.

   Controleer na de installatie of MentalRay beschikbaar is in Maya.

1. Voeg het pad naar de uitvoerbare map Maya toe aan de omgevingsvariabele PATH van Windows.

   Tik bijvoorbeeld op Windows Server 2012 op **[!UICONTROL Start]> [!UICONTROL Control Panel] > [!UICONTROL System and Security] > [!UICONTROL System] > [!UICONTROL Advanced System Settings] >[!UICONTROL Environment Variables]**. Voeg het volledige pad naar de map `Maya2016\bin` toe aan de systeemvariabele `Path`.

   ![chlimage_1-53](assets/chlimage_1-53.png)

1. Als u Maya wilt inschakelen voor opnemen en renderen, opent u **[!UICONTROL CRXDE Lite]** en navigeert u naar `/libs/settings/dam/v3D/assetTypes/maya` en stelt u de eigenschap **[!UICONTROL Enabled]** in op `true`.

   ![image2018-6-22_12-42-7](assets/image2018-6-22_12-42-7.png)

1. Als u de bestandsindeling JT (Siemens PLM Open CAD) wilt inschakelen, navigeert u naar `/libs/settings/dam/v3D/assetTypes/jt` en stelt u de eigenschap **[!UICONTROL Enabled]** in op `true`.
1. Schakel in AEM Maya in als renderer. Begin door naar **[!UICONTROL Tools > General > CRXDE Lite]** te navigeren.
1. Navigeer op de pagina **[!UICONTROL CRXDE Lite]** in het linkerdeelvenster naar het volgende:

   `/libs/settings/dam/v3D/renderers/maya`

   ![image2018-6-22_12-46-18](assets/image2018-6-22_12-46-18.png)

1. Stel de eigenschap **[!UICONTROL Enabled]** in op `true`.

1. Tik in de linkerbovenhoek van de pagina **[!UICONTROL CRXDE Lite]** op **[!UICONTROL Save All]**.

   Maya is nu ingeschakeld als een renderer.

## De integratie van AEM 3D testen met Autodesk Maya {#testing-the-integration-of-aem-d-with-autodesk-maya}

1. Open AEM Assets en upload de `.MA` bestanden in `sample-3D-content/models` naar de map `test3d`.

   `sample-3D-content.zip` is eerder gedownload voor validatie van de standaard 3D-functionaliteit.

1. Keer aan **[!UICONTROL Card]** mening terug en bekijk de berichtbanners die op de geupload activa worden getoond.

   De banner Converting Format wordt weergegeven terwijl Maya de native `.MA`-indeling converteert naar `.FBX`.

1. Nadat alle verwerking is voltooid, opent u het `logo-sphere.ma`-element en selecteert u het `stage-helipad.ma`-werkgebied.

   De ervaring van de Voorproef is het zelfde als met `logo_sphere.fbx` en `stage-helipad.fbx`.

1. Tik in de linkerbovenhoek van de pagina of klik op de vervolgkeuzelijst en selecteer **[!UICONTROL CRender]**.

   ![chlimage_1-54](assets/chlimage_1-54.png)

1. Selecteer **[!UICONTROL Autodesk Maya]** in de vervolgkeuzelijst **[!UICONTROL Renderer]** en tik vervolgens op **[!UICONTROL Start Render]**.
1. Tik in de rechterbovenhoek van de pagina of klik op **[!UICONTROL Close]** om terug te keren naar de weergave **[!UICONTROL Card]**.

   Bekijk de berichtenbanner op het afbeeldingselement dat wordt weergegeven (`logo-sphere`, tenzij een andere afbeeldingsnaam is opgegeven). Een voortgangsbalk op de banner geeft de voortgang van het renderen weer.

   >[!NOTE]
   >
   >Renderen is erg CPU-intensief en kan enkele minuten duren.

1. Nadat de rendering is voltooid, opent u het gerenderde afbeeldingselement.

   Controleer of de gerenderde afbeelding redelijk overeenkomt met de afbeelding die u bekeek op het moment dat u **[!UICONTROL Render Now]** klikte.

## Extra indelingen inschakelen die worden ondersteund door Maya {#enabling-additional-formats-supported-by-maya}

(Optioneel) Maya ondersteunt een aantal 3D-invoerindelingen, waarvan alle kunnen worden ingeschakeld zodat AEM het bestandstype herkent. Als deze optie is ingeschakeld, stuurt AEM het bestand naar Maya om het om te zetten in een indeling die direct door AEM kan worden ingeslikt.

Afhankelijk van de indeling kan de ondersteuning van functies beperkt zijn (materialen kunnen bijvoorbeeld niet worden doorgegeven) en kan de kwaliteit/betrouwbaarheid beperkt zijn (bijvoorbeeld omgekeerde vlakken). Adobe ondersteunt alleen het algemene mechanisme, maar geen specifieke indelingsconversie.

Zie [Ondersteunde indelingen voor het importeren van gegevens | Maya](https://knowledge.autodesk.com/support/maya/learn-explore/caas/CloudHelp/cloudhelp/2016/ENU/Maya/files/GUID-69BC066D-D4D8-4B12-900C-CF42E798A5D6-htm.html) voor informatie over de door Maya ondersteunde indelingen.

**Extra indelingen inschakelen die worden ondersteund door AEM**:

1. Navigeer met **[!UICONTROL CRXDE Lite]** naar `/libs/settings/dam/v3D/assetTypes`.
1. Maak een kopie van het knooppunt **[!UICONTROL jt]**. Klik met de rechtermuisknop op het knooppunt **[!UICONTROL jt]** en selecteer **[!UICONTROL Copy]**, klik vervolgens met de rechtermuisknop op de map **[!UICONTROL assetTypes]** en selecteer **[!UICONTROL Paste]**. Dit zou een nieuw knooppunt `/apps/cq-scene7-v3D/config/assetTypes/Copy of jt` moeten veroorzaken.
1. Wijzig de naam van het nieuwe knooppunt om het een unieke naam te geven die het bestandstype vertegenwoordigt dat moet worden toegevoegd. Het achtervoegsel van het bestand kan worden gebruikt of een andere unieke id.

1. Stel de eigenschap **[!UICONTROL Enabled]** van het nieuwe knooppunt in op `true`.

1. Stel de eigenschap **[!UICONTROL Extension]** van de nieuwe notitie in op het achtervoegsel/de extensie van het bestand dat wordt toegevoegd.
1. Stel de eigenschap **[!UICONTROL MimeType]** in op een geschikte waarde. `application/x-` gevolgd door de waarde van de  **[!UICONTROL Extension]** eigenschap zou voor de meeste bestandstypen moeten werken.
1. Zorg ervoor dat de eigenschap **[!UICONTROL Conversion]** is ingesteld op `fbx` en **[!UICONTROL IngestRegime]** op `Maya`.
1. Klik op **[!UICONTROL Save All]** linksboven op de pagina.

De volgende schermafbeelding illustreert een toegevoegde bestandsindeling, waarbij COLLADA DAE als voorbeeld wordt gebruikt:

![image2018-6-22_12-50-39](assets/image2018-6-22_12-50-39.png)

