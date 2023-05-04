---
title: Instellingen voor accountvergrendeling configureren
seo-title: Configure account-locking settings
description: Gebruik de optie Account vergrendelen inschakelen om gebruikersaccounts te vergrendelen na een opgegeven aantal opeenvolgende verificatiefouten.
seo-description: Use the Enable Account Locking option to lock user accounts after a specified number of consecutive authentication failures.
uuid: 5ff3fb76-8b11-4818-9a75-40ed8e121da5
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/setting_up_and_managing_domains
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d4409c6b-f4ef-499c-8daa-e93a163ff8ab
exl-id: e407c643-5753-447e-ad4e-deb7b9eb2b55
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# Instellingen voor accountvergrendeling configureren {#configure-account-locking-settings}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Wanneer u een domein toevoegt, geeft u op of accountvergrendeling moet worden ingeschakeld. Als de optie Account vergrendelen inschakelen is geselecteerd, worden gebruikersaccounts vergrendeld na een opgegeven aantal opeenvolgende verificatiefouten. Na een opgegeven periode kan de gebruiker opnieuw proberen te verifiëren. Met deze functie voorkomt u dat gebruikers verschillende aanmeldingscombinaties proberen te openen.

De montages van het gebruik op de pagina van het Beheer van het Domein om het maximumaantal authentificatiemislukkingen en de tijdsduur te specificeren dat de rekeningen worden gesloten. Deze instellingen zijn van toepassing op alle domeinen waarvoor accountvergrendeling is ingeschakeld.

1. Klik in de beheerconsole op **[!UICONTROL Settings > User Management > Domain Management]**.
1. Voer in het vak Maximum aantal opeenvolgende verificatiefouten het aantal opeenvolgende keren in dat een gebruiker zich zonder succes kan aanmelden voordat zijn account is vergrendeld. De standaardwaarde is 20.
1. Voer in het vak Account ontgrendelen na (minuten) het aantal minuten in dat de gebruikersaccount is vergrendeld. Na het opgegeven aantal minuten kan de gebruiker opnieuw proberen zich aan te melden. De standaardwaarde is 30.
1. Klik op **[!UICONTROL Save]**.
