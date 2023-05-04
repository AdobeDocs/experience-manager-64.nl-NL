---
title: De volgorde van de evaluatie voor verificatie wijzigen
seo-title: Change the order of evaluation for authentication
description: U kunt de volgorde wijzigen waarin AEM formulieren meerdere verificatieproviders evalueren.
seo-description: You can change the order in which AEM forms evaluates multiple authentication providers.
uuid: c2693e5b-cf09-4bb8-815a-2b20ebf6eea0
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_user_management
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 5434df9c-ecf6-450a-aa7e-d9ab69b66fe6
exl-id: cac16c50-a85d-4e40-a590-8a0a52be893c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---

# De volgorde van de evaluatie voor verificatie wijzigen {#change-the-order-of-evaluation-for-authentication}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als u meerdere verificatieproviders hebt geconfigureerd, kunt u de volgorde wijzigen waarin AEM formulieren deze evalueren voor verificatie. De orde van de authentificatieleveranciers die in het config.xml- dossier worden vermeld bepaalt de orde van evaluatie voor authentificatie.

1. Klik in de beheerconsole op Instellingen > Gebruikersbeheer > Configuratie > Configuratiebestanden importeren en exporteren.
1. Als u de huidige configuratie-instelling naar een bestand wilt exporteren, klikt u op Exporteren en slaat u het configuratiebestand op een andere locatie op.
1. Zoek het volgende knooppunt in het bestand:

   ```as3
    <node name="AuthSchemes"> 
        <map />  
            <node name="CertificateAuth"> 
                <map> 
                    <entry key="order" value="3" />  
                    <entry key="name" value="edc.server.auth.scheme.certificate" />  
                </map> 
        </node> 
        <node name="Kerberos"> 
            <map> 
                <entry key="kerberosSPN" value="defaultSPN" />  
                <entry key="order" value="1" />  
                <entry key="name" value="edc.server.auth.scheme.kerberos" />  
            </map> 
    </node>
   ```

   In `<entry key="order" value="3" />`, geef de waarde voor elke knoop uit om de orde van de authentificatieevaluatie te plaatsen.

1. Als u het bijgewerkte bestand wilt importeren, klikt u in Gebruikersbeheer op Configuratie > Configuratiebestanden importeren en exporteren.
1. Klik op Bladeren om het bestand te zoeken, klik op Importeren en klik vervolgens op OK.
