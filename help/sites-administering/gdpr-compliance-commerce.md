---
title: AEM handel - gereedheid van de GDPR
seo-title: AEM handel - gereedheid van de GDPR
description: 'null'
seo-description: 'null'
uuid: 7ca26587-8cce-4c75-8629-e0e5cfb8166c
contentOwner: carlino
discoiquuid: c637964a-dfcb-41fe-9c92-934620fe2cb3
translation-type: tm+mt
source-git-commit: 0db56cb77628b3e81b69382a314c30b43887bde6
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---


# AEM handel - gereedheid van de GDPR{#aem-commerce-gdpr-readiness}

>[!IMPORTANT]
>
>GDPR wordt in de onderstaande secties als voorbeeld gebruikt, maar de betreffende details zijn van toepassing op alle regels inzake gegevensbescherming en privacy; zoals GDPR, CCPA enz.

De algemene gegevensbeschermingsverordening van de Europese Unie betreffende de bescherming van persoonsgegevens treedt in werking in mei 2018. Zie de pagina [GDPR in het Adobe Privacy Center](https://www.adobe.com/privacy/general-data-protection-regulation.html)voor meer informatie.

>[!NOTE]
>
>Zie [AEM GDPR-gereedheid](/help/managing/data-protection-and-privacy.md) voor meer informatie.

![screen_shot_2018-03-22at111606](assets/screen_shot_2018-03-22at111606.jpg)

In onze out-of-the-box Integraties van de Handel, is AEM de ervaringslaag, die de diensten verbruikt en gegevens terugstuurt naar het platform van de klantenhandel dat op een headless wijze loopt.

Voor sommige handelsplatforms, slaan wij profielinformatie ( `/home/users`) en handelstkens (aan login in het handelsplatform) in AEM op. Lees voor deze gebruiksgevallen de [GDPR-verzoeken voor het AEM Platform](/help/sites-administering/handling-gdpr-requests-for-aem-platform.md)af.

![screen_shot_2018-03-22at111621](assets/screen_shot_2018-03-22at111621.jpg)

## Afhandeling van GDPR-verzoeken om AEM handel {#handling-gdpr-requests-for-aem-commerce}

Voor de integratie van de Salesforce-Commerce Cloud slaat AEM Commerce geen relevante GDPR-informatie op. U moet het verzoek doorsturen naar de [Salesforce Cloud](https://documentation.demandware.com/).

Voor de hybris- en IBM WebSphere-integratie zijn er gegevens in AEM. U moet de GDPR-instructies [van het](/help/sites-administering/handling-gdpr-requests-for-aem-platform.md) Platform gebruiken en de volgende vragen in overweging nemen:

1. **Waar worden mijn gegevens opgeslagen/gebruikt?** In de cache geplaatste gegevens van gebruikersprofielen, zoals naam, handelgebruikers-id, token, wachtwoord, adresgegevens, enzovoort, worden AEM weergegeven.
1. **Met wie deel ik de gedekte GDPR-gegevens?** Een bijwerking van relevante GDPR-gegevens in AEM Handel wordt niet opgeslagen (behalve relevante profielinformatie, zoals hierboven vermeld), maar wordt doorgestuurd naar het handelsplatform.
1. **Hoe kan ik mijn gebruikersgegevens** verwijderen? Verwijder het gebruikersprofiel in AEM en activeer de gebruikersverwijdering op het handelsplatform.

>[!NOTE]
>
>Heb een blik bij de [hybris wiki](https://wiki.hybris.com/) of de documentatie [van de Handel van](https://www-01.ibm.com/support/docview.wss?uid=swg27036450) Websphere indien vereist.

