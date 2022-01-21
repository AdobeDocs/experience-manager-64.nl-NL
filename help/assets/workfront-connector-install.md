---
title: Installeren [!DNL Workfront for Experience Manager enhanced connector]
description: Installeren [!DNL Workfront for Experience Manager enhanced connector]
role: Admin
feature: Integrations
source-git-commit: 18901a6b1e5035e16cb4f30a040ec8a42f704d87
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---


# Installeren [!DNL Workfront for Experience Manager enhanced connector] {#assets-integration-overview}

Een gebruiker met beheerdertoegang in [!DNL Adobe Experience Manager] installeert de verbeterde schakelaar. Bekijk voordat u gaat installeren de platformondersteuning en andere [eerste vereisten voor de aansluiting](https://one.workfront.com/s/csh?context=2467&amp;pubname=the-new-workfront-experience).

>[!IMPORTANT]
>
>Adobe vereist plaatsing en configuratie van [!DNL Adobe Workfront for Experience Manager enhanced connector] alleen via gecertificeerde partners of [!DNL Adobe Professional Services]. Indien opgesteld en gevormd zonder een verklaarde partner of [!DNL Adobe Professional Services], wordt deze niet ondersteund door Adobe.
>
>Adobe kan updates voor [!DNL Adobe Workfront] en [!DNL Adobe Experience Manager] die deze aansluiting overbodig maken; als dit voorkomt, kunnen de klanten worden vereist om van het gebruik van deze schakelaar over te gaan.

Voer de volgende stappen uit om de aansluiting te installeren:

1. Download de connector van [[!DNL Software Distribution] link](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/product/assets/workfront-tools.ui.apps.zip).

1. [De firewall configureren](https://one.workfront.com/s/document-item?bundleId=the-new-workfront-experience&amp;topicId=Content%2FAdministration_and_Setup%2FGet_started-WF_administration%2Fconfigure-your-firewall.html).

1. Toestaan dat in de verzender HTTP-headers met de naam `authorization`, `username`, en `apikey`. Toestaan `GET`, `POST`, en `PUT` verzoeken om `/bin/workfront-tools`.

1. Controleer of de volgende paden niet bestaan in [!DNL Experience Manager] opslagplaats:

   * `/apps/dam/gui/coral/components/admin/schemaforms/formbuilder`
   * `/apps/dam/gui/coral/components/admin/folderschemaforms/formbuilder`
   * `/apps/dam/gui/content/foldermetadataschemaeditor`
   * `/apps/dam/cfm/models/editor/components/datatypeproperties`
   * `/apps/settings/dam/cfm/models/formbuilderconfig`

1. Het pakket installeren met [!UICONTROL Package Manager]. Zie voor informatie over het installeren van pakketten [Documentatie pakketbeheer](/help/sites-administering/package-manager.md).

1. Maken `wf-workfront-users` in [!DNL Experience Manager] Gebruikersgroep en de machtiging toewijzen `jcr:all` tot `/content/dam`.

Een systeemgebruiker `workfront-tools` wordt automatisch gemaakt en de vereiste machtigingen worden automatisch beheerd. Alle gebruikers van [!DNL Workfront] die de schakelaar gebruiken wordt automatisch toegevoegd als deel van deze groep.

## De verbinding configureren tussen [!DNL Experience Manager] en [!DNL Workfront] {#configure-connection}

Ga als volgt te werk om een verbinding met Workfront te maken:

1. In [!DNL Experience Manager] selecteert u **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Workfront Tools Configuration]**.

1. Selecteren `workfront-tools` in het linkerdeelvenster en selecteer **[!UICONTROL Create]** in de rechterbovenhoek van de pagina.

1. In de **[!UICONTROL Workfront Connection]** de vereiste gegevens over uw [!DNL Workfront] implementatie en selecteer **[!UICONTROL Connect to Workfront]** optie. Wanneer de verbinding is gelukt, wordt de [!DNL Workfront] aangepaste documentintegratie wordt automatisch gemaakt in het dialoogvenster [!DNL Workfront] milieu.

   ![Verbinden [!DNL Experience Manager] en [!DNL Workfront]](/help/assets/assets/wf-connection-config.png)

1. Als u de verbinding wilt controleren, opent u deze in [!DNL Workfront] en controleert u of de API-sleutel gelijk is en of de verbinding **[!UICONTROL Enabled]**. Selecteer **[!UICONTROL Setup]** > **[!UICONTROL Documents]** > **[!UICONTROL Custom Integrations]** in [!DNL Workfront].