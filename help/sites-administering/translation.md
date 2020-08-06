---
title: Inhoud vertalen voor meertalige sites
seo-title: Inhoud vertalen voor meertalige sites
description: Leer hoe u inhoud voor meertalige sites vertaalt.
seo-description: Leer hoe u inhoud voor meertalige sites vertaalt.
uuid: b8047f6f-e86a-495d-9b80-731ac7d83c66
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: site-features
content-type: reference
discoiquuid: 67faa2ee-cb12-44b0-8bfb-534d1d6c360a
legacypath: /content/docs/en/aem/6-0/administer/integration/third-party-services/machine-translation
translation-type: tm+mt
source-git-commit: 7b39a715166eeefdf20eb22a4449068ff1ed0e42
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---


# Inhoud vertalen voor meertalige sites{#translating-content-for-multilingual-sites}

Automatiseer de vertaling van pagina-inhoud, elementen en door de gebruiker gegenereerde inhoud om meertalige websites te maken en te onderhouden. Om vertaalworkflows te automatiseren, integreert u de leveranciers van vertaaldiensten met AEM en creeert projecten voor het vertalen van inhoud in veelvoudige talen. AEM ondersteunt workflows voor het vertalen van mensen en machines.

* Menselijke vertaling: Inhoud wordt naar uw vertaalbureau verzonden en door professionele vertalers vertaald. Wanneer de vertaalde inhoud is voltooid, wordt deze geretourneerd en in AEM geïmporteerd. Wanneer uw vertaalbureau is geïntegreerd met AEM, wordt de inhoud automatisch verzonden tussen AEM en de vertaalprovider.
* Machinevertaling: De vertaalservice van de computer zet uw inhoud onmiddellijk om.

Voor het vertalen van inhoud worden de volgende stappen uitgevoerd:

1. [Sluit AEM aan bij uw vertaalserviceprovider](/help/sites-administering/tc-tic.md#connecting-to-a-translation-service-provider) en [maak configuraties](/help/sites-administering/tc-tic.md)voor vertaalintegratie.

1. [Koppel de pagina&#39;s van uw master](/help/sites-administering/tc-tic.md#configuring-pages-for-translation) taal aan de vertaalservice en frameworkconfiguraties.
1. [Identificeer het type inhoud](/help/sites-administering/tc-rules.md) dat u wilt vertalen.
1. [Bereid de inhoud voor vertaling](/help/sites-administering/tc-prep.md) voor door de master taal te ontwerpen en de basispagina&#39;s van taalkopieën te maken.
1. [Maak vertaalprojecten](/help/sites-administering/tc-manage.md) om de inhoud te verzamelen die u wilt vertalen en om het vertaalproces voor te bereiden.
1. Gebruik de vertaalprojecten om het vertaalproces [van de inhoud te](/help/sites-administering/tc-manage.md)beheren.

Als uw vertaalservicebureau geen aansluiting voor integratie met AEM biedt, ondersteunt AEM het handmatig extraheren en opnieuw invoegen van vertaalinhoud in XML-indeling.

>[!NOTE]
>
>Uw gebruiker moet een lid van de project-beheerders groep zijn om de eigenschappen van het Exemplaar van de Taal te gebruiken.

## Best practices voor {#best-practices}

De pagina Aanbevolen werkwijzen voor [vertaling](/help/sites-administering/tc-bp.md) bevat belangrijke informatie over uw implementatie.
