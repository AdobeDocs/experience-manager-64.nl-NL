---
title: Single Sign On en timeout handlers
seo-title: Single Sign On en timeout handlers
description: Hoe kan ik de time-outwaarde voor sessies instellen voor de AEM Forms-werkruimte.
seo-description: Hoe kan ik de time-outwaarde voor sessies instellen voor de AEM Forms-werkruimte.
uuid: 17583fd5-6453-41d3-bb63-a639983fbea9
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 698990a2-dd3f-480f-9d15-d87563860297
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---


# Single Sign On en timeout handlers {#single-sign-on-and-timeout-handlers}

AEM Forms-werkruimte is SSO ingeschakeld. Als een gebruiker zich heeft aangemeld bij een AEM Forms-toepassing, zoals de gebruikersinterface van Forms Manager of PDF Generator, en in dezelfde browsersessie toegang krijgt tot de AEM Forms-werkruimte, wordt de gebruiker aangemeld bij de AEM Forms-werkruimte en andersom.

## Time-out van server afhandelen in AEM Forms-werkruimte {#handling-server-timeout-in-nbsp-aem-forms-workspace}

De onderbreking van de zitting voor een gebruiker kan in de Console van het Beleid worden gevormd.

Als u de time-out wilt instellen, meldt u zich aan `https://[server]:[port]/adminui`en gaat u naar **Instellingen > Gebruikersbeheer > Configuratie > Geavanceerde systeemkenmerken** configureren en geeft u de gewenste instellingen op.

In de AEM Forms-werkruimte wordt de time-out verwerkt als:

* De duur van de zitting voor een gebruiker is beschikbaar in antwoord op `initialize` vraag die gebruikerszitting initialiseert.
* Een pop-updialoogvenster geeft een melding aan de gebruiker dat de sessie bijna verlopen is, 15 seconden voor de sessievervaldatum.

In dit pop-updialoogvenster:

* Klik op OK om de gebruikerssessie te beëindigen.
* Klik op Annuleren om de gebruikerssessie opnieuw te initialiseren.

>[!NOTE]
>
>Als geen actie wordt ondernomen, wordt de gebruiker automatisch geregistreerd uit de werkruimte van AEM Forms drie seconden vóór de zittingsafloop.
