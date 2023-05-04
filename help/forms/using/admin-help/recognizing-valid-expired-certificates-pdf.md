---
title: Geldige en verlopen certificaten in PDF-documenten herkennen
seo-title: Recognizing valid and expired certificates in PDF documents
description: Leer hoe u geldige en verlopen certificaten in PDF-documenten herkent.
seo-description: Learn how to recognize valid and expired certificates in PDF documents.
uuid: ceeff57a-586f-4f7b-852f-2a637f003d7e
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_acrobat_reader_dc_extensions
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 4559218a-65ba-4577-ad26-7721e28971bc
exl-id: 6e2c109c-381f-455d-bd1d-b08c37c0bd67
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---

# Geldige en verlopen certificaten in PDF-documenten herkennen {#recognizing-valid-and-expired-certificates-in-pdf-documents}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Wanneer een document van de PDF dat gebruiksrechten heeft door de Uitbreidingen van de Reader worden toegepast in Adobe Reader wordt geopend, verschijnt een statusbar die de specifieke gebruiksrechten beschrijft die in het document van de PDF worden toegelaten.

Wanneer het digitale certificaat dat de gebruiksrechten voor een PDF-document opgeeft, verloopt en het PDF-document in Adobe Reader wordt geopend, wordt een dialoogvenster weergegeven waarin de gebruiker wordt gewaarschuwd dat het PDF-document gebruiksrechten heeft, maar deze rechten zijn uitgeschakeld. Hoewel het bericht aangeeft dat het PDF-document is gewijzigd of gewijzigd, is dit niet altijd het geval. Adobe Reader geeft dit bericht weer wanneer een certificaat verloopt of een document wordt gewijzigd. In Adobe Reader 7.0.x of hoger kunt u niet bepalen welk geval momenteel aan de orde is.

Nadat u het dialoogvenster hebt gesloten, opent Adobe Reader het PDF-document. De gebruiksrechten die zijn toegepast met Acrobat Reader DC-extensies zijn niet beschikbaar, zoals u had verwacht. Als het PDF-document een interactief formulier is, worden de formuliervelden vergrendeld en kan de gebruiker de formuliergegevens niet wijzigen.
