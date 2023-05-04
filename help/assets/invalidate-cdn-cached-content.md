---
title: Uw CDN-gecachete content ongeldig maken
seo-title: Invalidating your CDN cached content
description: Door de CDN-inhoud (Content Delivery Network) in de cache te ongeldig te maken, kunt u snel elementen bijwerken die door Dynamic Media worden geleverd, in plaats van te wachten tot de cache verloopt.
seo-description: Invalidating your CDN (Content Delivery Network) cached content lets you quickly update assets that are delivered by Dynamic Media, instead of waiting for the cache to expire.
uuid: 0fd88e31-9745-4c98-a245-9f5d0766cad4
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: e6c9b50b-c27c-48bf-b3c0-9994e7bf6d7e
exl-id: 335c7a78-a00f-451b-8e53-225830d429c6
feature: Asset Management,CDN Cache
role: Admin,User,Developer
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 27%

---

# Uw CDN-gecachete content ongeldig maken {#invalidating-your-cdn-cached-content}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Dynamic Media-elementen worden door de CDN in cache geplaatst voor snelle levering. Wanneer u echter updates aan een element aanbrengt, wilt u deze wijzigingen mogelijk direct van kracht laten worden. Door de CDN-inhoud (Content Delivery Network) in de cache te ongeldig te maken, kunt u snel elementen bijwerken die door Dynamic Media worden geleverd, in plaats van te wachten tot de cache verloopt.

Zie ook [Overzicht van cache in Dynamic Media Classic](https://helpx.adobe.com/experience-manager/scene7/kb/base/caching-questions/scene7-caching-overview.html).

**Om uw CDN caching inhoud ongeldig te maken:**

1. Meld u aan bij uw Dynamic Media Classic-bureaubladtoepassing.

   [Dynamic Media Classic-bureaubladtoepassing](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/intro/dynamic-media-classic-desktop-app.html#system-requirements-dmc-app)

   Uw geloofsbrieven en opening van een sessie werden verstrekt door Adobe op het tijdstip van levering. Neem contact op met Technische ondersteuning als u deze informatie niet hebt.

1. Klik op **[!UICONTROL Setup > Application Setup > General Settings]**.
1. Zoek op de pagina Algemene instellingen van toepassing onder de kop Servers van de groep de locatie **[!UICONTROL CDN Invalidation Template]** tekstvak.

1. Geef de sjabloon op die wordt gebruikt voor het ongeldig maken van de CDN-cache (Content Delivery Network).

   Stel dat u bijvoorbeeld een afbeeldings-URL invoert (inclusief voorinstellingen of wijzigingstoetsen voor afbeeldingen) die verwijst naar `<ID>`in plaats van een specifieke afbeelding-id zoals in het volgende voorbeeld:

   `https://server.com/is/image/Company/<ID>?$product$`

   Als de sjabloon alleen bevat `<ID>`en vervolgens vult Dynamic Media in `https://<server>/is/image` waar `<server>` is de naam van de publicatieserver die is gedefinieerd in Algemene instellingen en &lt;id> is het geselecteerde middel of de middelen om ongeldig te worden gemaakt.

1. Klik in de rechterbenedenhoek van de pagina op **[!UICONTROL Close]**.
1. Selecteer in de gebruikersinterface van de Dynamic Media Classic-bureaubladtoepassing een of meer elementen en klik vervolgens op **[!UICONTROL File > Invalidate CDN]**. Er wordt een lijst weergegeven met een of meer URL&#39;s die zijn gegenereerd op basis van de sjabloon die u hebt gemaakt en de elementen die u hebt geselecteerd. De URL van de server wordt gebruikt onder &quot;Gepubliceerde servernaam&quot; onder Algemene instellingen van toepassing.

   Stel dat u, terwijl de CDN-validatiesjabloon in de vorige stap is ingesteld, één afbeelding met afbeeldingselementen hebt geselecteerd met de naam `Backpack_B`. Wanneer u op **[!UICONTROL File > Invalidate CDN]** het resulteert in de volgende geproduceerde URL in het gebruikersinterface van de Bevestiging CDN:

   `https://server.com/is/image/Company/Backpack_B?$product$`

1. Klik in de lijst URL op **[!UICONTROL Continue]** om de cache voor elke specifieke URL te wissen. U kunt een URL bewerken of u kunt een URL toevoegen door deze in het vak URL-lijst te typen of te plakken. u hoeft CDN niet vooraf in te stellen om sjabloon ongeldig te maken.

   Nadat u op **[!UICONTROL Continue]** Er wordt een indicator weergegeven die u een schatting geeft van hoe lang het duurt om de cache te wissen.

   Als u meerdere assets hebt geselecteerd en vervolgens op **[!UICONTROL File > Invalidate CDN]** hebt geklikt, wordt naar elke asset verwezen in de opgeslagen **[!UICONTROL Template URL]**. Daarom kunt u een **[!UICONTROL CDN Invalidate Template]** definiëren waarin naar elke voorinstelling voor URL-afbeeldingen wordt verwezen waarnaar op uw website wordt verwezen (zoals productdetails, zoekresultaten, enz.). Wanneer u vervolgens een of meer afbeeldingen selecteert om ongeldig te worden gemaakt door het cachegeheugen, vullen de URL&#39;s automatisch de interface in.

   >[!NOTE]
   >
   >Wanneer u assets selecteert en vervolgens op **[!UICONTROL File > Invalidate CDN]** klikt, gebruikt Dynamische media een ongeldige CDN-sjabloon om automatisch URL&#39;s te maken om ongeldig te maken vanaf het CDN (Content Delivery Network). Als het tekstvak **[!UICONTROL CDN Invalidate Template]** leeg is, wordt er een lege URL-lijst weergegeven. Caching bij CDN is niet gebaseerd op assets; het is gebaseerd op URL. Daarom moet u de volledige URL&#39;s die op uw website staan, kennen. Nadat u deze URL&#39;s hebt bepaald, kunt u ze eerder in de stappen toevoegen aan het tekstvak **[!UICONTROL Invalidate CDN Template]**. Vervolgens kunt u deze assets selecteren en de URL&#39;s in één stap ongeldig maken.
   >
   >U kunt ook volledige URL&#39;s toevoegen aan de **[!UICONTROL Invalidate CDN]** lijst. Als u deze aanpak volgt, is het niet nodig om elementen in Dynamic Media Classic te selecteren voordat u naar de **[!UICONTROL File > Invalidate CDN]** optie.
