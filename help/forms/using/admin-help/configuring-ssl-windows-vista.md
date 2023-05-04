---
title: SSL configureren onder Windows Vista
seo-title: Configuring SSL on Windows Vista
description: Leer hoe te om SSL op Windows Vista te vormen.
seo-description: Learn how to configure SSL on Windows Vista.
uuid: 20bfcefb-ec84-4c55-bceb-6af106d883d7
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_ssl
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 667645a0-53d0-4f9b-a0ba-cc7e366a23a1
exl-id: 8eee2ed2-8263-47f2-b928-214fd9ab5f6e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# SSL configureren onder Windows Vista {#configuring-ssl-on-windows-vista}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Om SSL op Windows Vista™ te vormen, hebt u een SSL certificaat met sleutels van RSA voor authentificatie nodig. U kunt het Java-sleutelgereedschap gebruiken om het certificaat te maken.

>[!NOTE]
>
>Windows Vista werkt niet met DSA-toetsen.

U kunt keytool uitvoeren met één opdracht die alle informatie bevat die nodig is om het certificaat en sleutelarchief te maken.

**Een SSL-certificaat maken**

1. In een bevelherinnering, navigeer aan *[JAVA HOME]*/bin en typ de volgende opdracht om het certificaat en sleutelarchief te maken:

   `keytool -genkey -keyalg RSA -dname "CN=`*Hostnaam* `, OU=`*Groepsnaam* `, O=`*Bedrijfsnaam* `,L=`*Plaats******Naam* `, S=`*Staat* `, C=`*Landcode* `" -alias`*&quot;LC Cert&quot;* `-keypass` `*key*`*_**password* `-keystore`*sleutelbestandsnaam* `.keystore`

   >[!NOTE]
   >
   >Vervangen *[JAVA_HOME] met de directory waarin de JDK is geïnstalleerd, en vervangt u de cursieve tekst door waarden die overeenkomen met uw omgeving.*

1. Type `changeit` als het wachtwoord. Dit wachtwoord is de standaardinstelling voor een Java-installatie en de systeembeheerder kan deze hebben gewijzigd.
