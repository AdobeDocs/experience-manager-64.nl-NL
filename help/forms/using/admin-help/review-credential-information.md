---
title: Gebruiksgegevens voor referentie controleren
seo-title: Review credential use information
description: Leer hoe u de gegevens over het gebruik van referenties kunt controleren.
seo-description: Learn how to review credential use information.
uuid: 02af75f9-c235-470d-a98b-a2102aa31381
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_acrobat_reader_dc_extensions
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: cdf61cff-768b-49f7-9926-400bc96b0708
exl-id: abd62cca-edf0-4b44-94c3-7af3116b0c54
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# Gebruiksgegevens voor referentie controleren {#review-credential-use-information}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De referentie bevat informatie over het bedoelde gebruik dat toegankelijk is via de Acrobat Reader DC-webtoepassing voor extensies voor eindgebruikers. U kunt deze informatie gebruiken om het type geïnstalleerde referentie (evaluatie of productie) en zijn geldigheidsdata te bepalen.

1. Open een webbrowser en voer de volgende URL in:

   http://localhost:*[poort]*/ReaderExtensions (waarbij *[poort]* is het poortnummer van de toepassingsserver)

1. Meld u aan met de standaardgebruikersnaam en het standaardwachtwoord:

   Gebruikersnaam: beheerder

   Wachtwoord: password

   >[!NOTE]
   >
   >U moet over beheerdersrechten of gebruikersrechten beschikken om u aan te melden met de standaardgebruikersnaam en het standaardwachtwoord. Als u andere gebruikers toegang wilt geven tot Acrobat Reader DC-extensies, maakt u de gebruikersaccounts in Gebruikersbeheer en kent u de webtoepassingsrol voor Acrobat Reader DC-extensies toe aan de gebruikers.

1. Selecteer de referentie-alias in de lijst Selecteer referentie en bekijk de informatie in de Vervaldatum en de gebruiksaanwijzing.

>[!NOTE]
>
>De vervaldatum van de referentie is ook beschikbaar op de pagina Settings > Trust Store Management > Local Credentials van de beheerconsole, onder Expiration Date.
