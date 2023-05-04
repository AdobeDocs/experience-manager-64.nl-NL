---
title: Componenten weergeven die zijn gebaseerd op de gebruikte sjabloon
seo-title: Displaying components based on the template used
description: Wanneer u een formulier maakt, leert u hoe u componenten in het zijpaneel kunt inschakelen op basis van de geselecteerde sjabloon.
seo-description: When you create a form, learn how you can enable components in the sidebar based on the template selected.
uuid: 4e87f400-fb45-413d-9be8-72edbe99f210
contentOwner: sashanka
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: customization
content-type: reference
discoiquuid: 940e45b4-dbf1-4207-bd4a-cf677d645fb4
exl-id: a4cee2e6-a56f-4355-8176-b3ed7478a775
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 1%

---

# Componenten weergeven die zijn gebaseerd op de gebruikte sjabloon {#displaying-components-based-on-the-template-used}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Wanneer een formulierauteur een adaptief formulier maakt met behulp van een [template](/help/forms/using/template-editor.md), kan de auteur van het formulier specifieke componenten zien en gebruiken die op sjabloonbeleid zijn gebaseerd. U kunt een beleid voor sjablooninhoud opgeven waarmee u een groep componenten kunt kiezen die de auteur van het formulier ziet op het moment van het ontwerpen van het formulier.

## Het inhoudsbeleid van een sjabloon wijzigen {#changing-the-content-policy-of-a-template}

Wanneer u een sjabloon maakt, wordt deze onder `/conf` in de inhoudsopslagplaats. Gebaseerd op de mappen die u hebt gemaakt in het dialoogvenster `/conf` map, pad naar uw sjabloon is: `/conf/<your-folder>/settings/wcm/templates/<your-template>`.

Voer de volgende stappen uit om de componenten in de zijbalk weer te geven op basis van het inhoudsbeleid van een sjabloon:

1. CRXDE-lijst openen.

   URL: `https://<server>:<port>/crx/de/index.jsp`

1. Navigeer in CRXDE naar de map waarin de sjabloon is gemaakt.

   Bijvoorbeeld: `/conf/<your-folder>/`

1. Navigeer in CRXDE naar: `/conf/<your-folder>/settings/wcm/policies/fd/af/layouts/gridFluidLayout/`

   Voor het selecteren van een groep componenten is een nieuw inhoudsbeleid vereist. Om een nieuw beleid tot stand te brengen, kopieer-kleef het standaardbeleid, en noem het anders.

   Het pad naar het standaard inhoudsbeleid is: `/conf/<your-folder>/settings/wcm/policies/fd/af/layouts/gridFluidLayout/default`

   In de `gridFluidLayout` , kopieert en plakt u het standaardbeleid en wijzigt u de naam ervan. Bijvoorbeeld, `myPolicy`.

   ![Standaardbeleid kopiëren](assets/crx-default1.png)

1. Selecteer het nieuwe beleid u creeert, en selecteer **componenten** eigenschap in het rechterdeelvenster met tekst `string[]`.

   Wanneer u het componentenbezit selecteert en opent, ziet u het Edit dialoog van Componenten. In het dialoogvenster Componenten bewerken kunt u componentgroepen toevoegen of verwijderen met de opdracht **+** en **-** knoppen. U kunt componentengroep toevoegen die componenten omvat die vorm u auteurs aan gebruik wilt.

   ![Componenten toevoegen aan of verwijderen uit het beleid](assets/add-components-list1.png)

   Nadat u een componentgroep hebt toegevoegd, klikt u op **OK** om de lijst bij te werken, en klik dan **Alles opslaan** boven CRXDE-adresbalk en vernieuwen.

1. Wijzig in de sjabloon het inhoudsbeleid van standaard in het nieuwe beleid dat u hebt gemaakt. ( `myPolicy` in dit voorbeeld.)

   Om het beleid, in CRXDE te veranderen, navigeer aan `/conf/<your-folder>/settings/wcm/templates/<your-template>/policies/jcr:content/guideContainer/rootPanel/items`.

   In de `cq:policy` eigenschap, wijzigen `default` op de nieuwe beleidsnaam ( `myPolicy`).

   ![Beleid voor bijgewerkte sjablooninhoud](assets/updated-policy.png)

   Wanneer u een formulier ontwerpt dat u met de sjabloon maakt, kunt u de toegevoegde componenten in het zijpaneel zien.
