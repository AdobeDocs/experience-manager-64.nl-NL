---
title: Onbetaalde e-mails bijhouden
seo-title: Tracking Bounced Emails
description: Wanneer u een nieuwsbrief naar veel gebruikers verzendt, bevat de lijst meestal enkele ongeldige e-mailadressen. Het verzenden van nieuwsbrieven naar die adressen stuitert terug. AEM kan die grenzen beheren en kan ophouden verzendend nieuwsbrieven naar die adressen te verzenden nadat de gevormde stuiterteller wordt overschreden.
seo-description: When you send a newsletter to many users, there are usually some invalid emails addresses in the list. Sending newsletters to those addresses bounce back. AEM is capable of managing those bounces and can stop sending newsletters to those addresses after the configured bounce counter is exceeded.
uuid: 749959f2-e6f8-465f-9675-132464c65f11
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: fde9027b-9057-48c3-ae34-3f3258c5b371
exl-id: 3be35bb8-3485-42a6-8195-c3e95d097856
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 0%

---

# Onbetaalde e-mails bijhouden{#tracking-bounced-emails}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>Adobe is niet van plan om het bijhouden van geopende/aangekondigde e-mails die door AEM SMTP-service worden verzonden, verder te verbeteren.
>
>De aanbeveling is: [Adobe Campaign en zijn AEM integratie benutten](/help/sites-administering/campaign.md).

Wanneer u een nieuwsbrief naar veel gebruikers verzendt, bevat de lijst meestal enkele ongeldige e-mailadressen. Het verzenden van nieuwsbrieven naar die adressen stuitert terug. AEM kan deze grenzen beheren en kan stoppen met het verzenden van nieuwsbrieven naar die adressen nadat de geconfigureerde stuiterteller is overschreden. Door gebrek, wordt het stuiterende tarief geplaatst aan 3 maar configureerbaar.

Als u AEM wilt instellen om teruggestuurde e-mails bij te houden, moet u AEM instellen om een bestaande postbus te opiniepeilen waar teruggestuurde e-mails worden ontvangen (dit is meestal het e-mailadres &#39;van&#39; dat u opgeeft waar u de nieuwsbrief verzendt). AEM opiniepeilt dit postvak en importeert alle e-mailberichten onder het pad dat in de stemconfiguratie is opgegeven. Vervolgens wordt een workflow geactiveerd om te zoeken naar de verzonden e-mailadressen binnen de gebruikers en wordt de eigenschapswaarde van bounceCounter van de gebruiker dienovereenkomstig bijgewerkt. Nadat de gevormde maximumgrenzen worden overschreden, wordt de gebruiker verwijderd uit de nieuwsbrief lijst.

## De importmodule voor diervoeders configureren {#configuring-the-feed-importer}

Met de importfunctie kunt u herhaaldelijk inhoud uit externe bronnen importeren in uw opslagplaats. Met deze configuratie van de voederimporteur, AEM controleert de brievenbus van de afzender op bekende e-mails.

De importmodule configureren voor het bijhouden van onaangekondigde e-mails:

1. In **Gereedschappen** selecteert u de importmodule voor diervoeders.

1. Klikken **Toevoegen** om een nieuwe configuratie te creëren.

   ![chlimage_1](assets/chlimage_1.png)

1. Voeg een nieuwe configuratie toe door het type te selecteren en informatie aan de opiniepeiling URL toe te voegen om de gastheer en de haven te vormen. Bovendien moet u wat post en protocol-specifieke parameters aan de vraag toevoegen URL. Stel de configuratie in op minstens eenmaal per dag.

   Alle configuraties hebben informatie nodig over het volgende in de opiniepeiling-URL:

   `username`: De gebruikersnaam die moet worden gebruikt voor verbinding

   `password`: Het wachtwoord dat moet worden gebruikt voor verbinding

   Afhankelijk van het protocol kunt u bovendien bepaalde instellingen configureren.

   **POP3-configuratie-eigenschappen:**

   `pop3.leave.on.server`: Bepaalt of om berichten op server al dan niet te verlaten. Ingesteld op true om berichten op de server te laten, anders false. Heeft als standaardwaarde true.

   **POP3-voorbeelden:**

   | pop3s://pop.gmail.com:995/INBOX?username=user&amp;password=secret | Pop3 via SSL gebruiken om verbinding te maken met GMail op poort 995 met gebruiker/geheim, zodat berichten standaard op de server blijven staan |
   |---|---|
   | pop3s://pop.gmail.com:995/INBOX?username=user&amp;password=secret&amp;pop3.leave.on.server=false | pop3s://pop.gmail.com:995/INBOX?username=user&amp;password=secret&amp;pop3.leave.on.server=false |

   **IMAP-configuratie-eigenschappen:**

   Hiermee kunt u markeringen instellen waarnaar u wilt zoeken.

   `imap.flag.SEEN`:Stel false in voor nieuwe/onzichtbare berichten, true voor al-gelezen berichten

   Zie [https://java.sun.com/products/javamail/javadocs/javax/mail/Flags.Flag.html](https://java.sun.com/products/javamail/javadocs/javax/mail/Flags.Flag.html) voor de volledige lijst van vlaggen.

   **IMAP-voorbeelden:**

   | imaps://imap.gmail.com:993/inbox?username=user&amp;password=secret | Het gebruiken van IMAP over SSL om met GMail op haven 993 met gebruiker/geheim te verbinden. Nieuwe berichten alleen standaard ophalen. |
   |---|---|
   | imaps://imap.gmail.com:993/inbox?username=user&amp;password=secret&amp;imap.flag.SEEN=true | Het gebruiken van IMAP over SSL om met GMail 93 met gebruiker/geheim te verbinden, slechts het krijgen van reeds gezien bericht. |
   | imaps://imap.gmail.com:993/inbox?username=user&amp;password=secret&amp;imap.flag.SEEN=true&amp;imap.flag.SEEN=false | Het gebruiken van IMAP over SSL om met GMail 93 met gebruiker/geheim te verbinden, die reeds wordt gelezen OF nieuwe berichten. |

1. Sla de configuratie op.

## De service-component voor nieuwsbrieven configureren {#configuring-the-newsletter-service-component}

Na het vormen van feed importeur, moet u van adres en stuiterteller vormen.

Om de nieuwsbrief dienst te vormen:

1. In de OSGi-console op `<host>:<port>/system/console/configMgr` en navigeer naar **MCM-nieuwsbrief**.

1. Configureer de service en sla de wijzigingen op wanneer u klaar bent.

   ![chlimage_1-1](assets/chlimage_1-1.png)

   De volgende configuraties kunnen worden ingesteld om het gedrag aan te passen:

   | Maximum voor stuitteller (max.bounce.count) | Bepaalt het aantal grenzen tot een gebruiker zal worden weggelaten wanneer het verzenden van een nieuwsbrief. Als u deze waarde instelt op 0, wordt de stuiteringscontrole volledig uitgeschakeld. |
   |---|---|
   | Activiteit geen cache (sent.activity.nocache) | Definieert de cache-instelling die moet worden gebruikt voor de verzonden activiteit van de nieuwsbrief |

   Zodra bewaard, doet de nieuwsbriefMCM dienst het volgende:

   * Schrijft een activiteit aan de gebruikers verborgen stroom na het succesvol verzenden van een nieuwsbrief.
   * Schrijft een activiteit als een stuit wordt ontdekt en de gebruikers stuiteren tegenveranderingen.
