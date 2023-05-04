---
title: Het vormen het Verwijderen eindpunten
seo-title: Configuring Remoting endpoints
description: Leer hoe te om remoting eindpunten te vormen.
seo-description: Learn how to configure remoting endpoints.
uuid: 4d4f9274-dcae-4b9f-975a-575376c2f89c
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/managing_endpoints
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: aab9d622-d76b-4100-9ca6-e5b86f543381
exl-id: d8e31f99-0558-4634-ae35-f4a09f34ad6d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---

# Het vormen het Verwijderen eindpunten {#configuring-remoting-endpoints}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met een extern eindpunt kan een toepassing die met Flex is gebouwd, de service aanroepen met (Verouderd voor AEM formulieren) AEM formulieren Remoting. Een remoting eindpunt wordt automatisch gecreeerd voor elke geactiveerde dienst. Een bestemming van Flex die de zelfde naam zoals het eindpunt heeft wordt gecreeerd, en de cliënten van Flex kunnen verre voorwerpen tot stand brengen die aan deze bestemming richten om verrichtingen op de relevante dienst aan te halen.

## Instellingen voor eindpunten verwijderen {#remoting-endpoint-settings}

**Flex-clientverificatiemethode:** Bepaalt het type van reactie dat de server terug naar de cliënt verzendt wanneer de aangehaalde dienst veiligheid toegelaten is, steunt de aangehaalde verrichting geen anonieme aanroepen, en de cliënt gaat of in geen of ongeldige geloofsbrieven over.
