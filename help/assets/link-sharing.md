---
title: Delen van koppelingen van middelen
description: Hoe te om activa, omslagen, en inzamelingen binnen Middelen AEM als URL aan externe partijen te delen.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1

---


# Delen van koppelingen van middelen {#asset-link-sharing}

Met Adobe Experience Manager (AEM) kunt u elementen, mappen en verzamelingen als een URL delen met leden van uw organisatie en externe entiteiten, waaronder partners en leveranciers. Het delen van elementen via een koppeling is een handige manier om bronnen beschikbaar te maken voor externe partijen zonder dat deze zich eerst hoeven aan te melden bij AEM Assets.

>[!NOTE]
>
>U vereist geeft ACL toestemming op de omslagen en de activa uit die u als verbinding wilt delen.

## Assets delen {#share-assets}

Gebruik het dialoogvenster Koppelen om de URL te genereren voor elementen die u met gebruikers wilt delen. Gebruikers met beheerdersrechten of met leesmachtigingen op de `/var/dam/share` locatie kunnen de koppelingen weergeven die met hen worden gedeeld.

>[!NOTE]
>
>Voordat u een koppeling met gebruikers deelt, moet u ervoor zorgen dat [!UICONTROL Day CQ Mail Service] is geconfigureerd. Er treedt een fout op als u een koppeling probeert te delen zonder eerst de Day CQ Mail Service [te](link-sharing.md#configure-day-cq-mail-service)configureren.

1. Selecteer in de gebruikersinterface Elementen het element dat u wilt delen als een koppeling.
1. Klik/tik op het pictogram **[!UICONTROL Delen van koppeling]** - ![](assets/assets_share.png)elementen delen op de werkbalk.

   Er wordt automatisch een elementkoppeling gemaakt in het veld Koppeling **** delen. Kopieer deze koppeling en deel deze met de gebruikers. De standaardvervaltijd voor de verbinding is één dag.

   ![Dialoogvenster met de koppeling Delen](assets/chlimage_1-542.png)

   Alternatief, ga te werk om stappen 3-7 van deze procedure uit te voeren om e-mailontvangers toe te voegen, de vervaltijd voor de verbinding te vormen, en het van de dialoog te verzenden.

   >[!NOTE]
   >
   >Als u koppelingen van uw AEM-auteur naar externe entiteiten wilt delen, stelt u alleen de volgende URL&#39;s beschikbaar die worden gebruikt voor het delen van koppelingen, voor GET-aanvragen. Blokkeer andere URL&#39;s om ervoor te zorgen dat uw AEM-implementatie veilig is.
   >
   >* &lt;AEM Server>/linkshare.html
   * &lt;AEM Server>/linksharepreview.html
   * &lt;AEM Server>/linkexpired.html


   >[!NOTE]
   Als een gedeeld element naar een andere locatie wordt verplaatst, werkt de koppeling niet meer. Maak de koppeling opnieuw en deel deze opnieuw met de gebruikers.

1. Van de Webconsole, open de Configuratie van de Verbinding External **[!UICONTROL van de Verbinding van]** Dag CQ en wijzig de volgende eigenschappen op het gebied van **[!UICONTROL Domeinen]** met de waarden die tegen elk worden vermeld:

   * lokaal
   * author
   * publish
   Geef voor de eigenschappen `local` en `author` de URL op voor respectievelijk de lokale instantie en de auteur. Zowel `local` als `author` eigenschappen hebben dezelfde waarde als u één AEM-auteurinstantie uitvoert. Geef `publish`bijvoorbeeld de URL op voor de publicatie-instantie.

1. Typ in het vak E-mailadres van het dialoogvenster **[!UICONTROL Delen]** van koppeling de e-mailid van de gebruiker met wie u de koppeling wilt delen. U kunt de koppeling ook delen met meerdere gebruikers.

   Als de gebruiker lid is van uw organisatie, selecteert u de e-mailid van de gebruiker in de voorgestelde e-mailadressen die worden weergegeven in de lijst onder het invoergebied. Voor een externe gebruiker typt u de volledige e-mailid en selecteert u deze in de lijst.

   Als u wilt dat e-mailberichten naar gebruikers kunnen worden verzonden, configureert u de SMTP-servergegevens in [Day CQ Mail Service](link-sharing.md#configure-day-cq-mail-service).

   ![Koppelingen naar elementen rechtstreeks delen via het dialoogvenster Koppelen](assets/chlimage_1-543.png)

   Koppelingen naar elementen rechtstreeks delen via het dialoogvenster Koppelen

   >[!NOTE]
   Als u een e-mailadres invoert van een gebruiker die geen lid is van uw organisatie, wordt het woord &quot;Externe gebruiker&quot; voorafgegaan door de e-mailid van de gebruiker.

1. Voer in het vak **[!UICONTROL Onderwerp]** een onderwerp in voor het element dat u wilt delen.
1. Voer in het vak **[!UICONTROL Bericht]** een optioneel bericht in.
1. Geef in het veld **[!UICONTROL Verlopen]** een vervaldatum en -tijd voor de koppeling op met de datumkiezer. De vervaldatum wordt standaard ingesteld voor een week vanaf de datum waarop u de koppeling deelt.

   ![Vervaldatum en -tijd instellen voor gedeelde koppeling](assets/chlimage_1-544.png)

1. Als u gebruikers de oorspronkelijke afbeelding samen met de uitvoeringen wilt laten downloaden, selecteert u **[!UICONTROL Downloaden van origineel bestand]** toestaan.

   >[!NOTE]
   Standaard kunnen gebruikers alleen de uitvoeringen downloaden van het element dat u als koppeling deelt.

1. Klik op **[!UICONTROL Delen]**. Een bericht bevestigt dat de koppeling via e-mail met de gebruiker(s) wordt gedeeld.
1. Als u het gedeelde element wilt weergeven, klikt of tikt u op de koppeling in het e-mailbericht dat naar de gebruiker is verzonden. Het gedeelde element wordt weergegeven op de pagina [!UICONTROL Adobe Marketing Cloud] .

   ![Gedeelde middelen zijn beschikbaar in Adobe Marketing Cloud](assets/chlimage_1-545.png)

   Als u wilt schakelen naar de lijstweergave, klikt of tikt u op het layoutpictogram op de werkbalk.

1. Als u een voorvertoning van het element wilt genereren, klikt of tikt u op het gedeelde element. Klik op **[!UICONTROL Terug]** op de werkbalk om de voorvertoning te sluiten en terug te keren naar de pagina [!UICONTROL Marketing Cloud] . Als u een map hebt gedeeld, klikt of tikt u op **[!UICONTROL Bovenliggende map]** om terug te keren naar de bovenliggende map.

   ![chlimage_1-546](assets/chlimage_1-546.png)

   >[!NOTE]
   AEM ondersteunt het genereren van een voorvertoning van elementen van deze MIME-typen: JPG, PNG, GIF, BMP, INDD, PDF en PPT. U kunt alleen de elementen van de andere MIME-typen downloaden.

1. Als u het gedeelde element wilt downloaden, klikt of tikt u op het pictogram **[!UICONTROL Selecteren]** op de werkbalk, klikt/tikt u op het element en klikt/tikt u op **[!UICONTROL Downloaden]** op de werkbalk.

   ![Werkbalkoptie om het gedeelde element te downloaden](assets/chlimage_1-547.png)

1. Als u de elementen die u als koppelingen hebt gedeeld, wilt weergeven, gaat u naar de interface Middelen en klikt of tikt u op het pictogram **[!UICONTROL GlobalNav]** . Kies **[!UICONTROL Navigatie]** in de lijst om het navigatievenster weer te geven.
1. Kies in het navigatievenster de optie **[!UICONTROL Gedeelde koppelingen]** om een lijst met gedeelde elementen weer te geven.
1. Als u een element niet meer wilt delen, selecteert u het en tikt u op de werkbalk op Delen **[!UICONTROL opheffen of klikt u op Delen]** opheffen. Een bericht bevestigt dat u het element niet hebt gedeeld. Bovendien wordt de vermelding voor het element uit de lijst verwijderd.

## CQ-mailservice op dag configureren {#configure-day-cq-mail-service}

1. Klik of tik het embleem AEM, en navigeer dan aan **[!UICONTROL Hulpmiddelen > Verrichtingen > de Console]** van het Web.
1. Zoek vanuit de lijst met services de **[!UICONTROL Day CQ Mail Service]**.
1. Klik op het pictogram **[!UICONTROL Bewerken]** naast de service en configureer de volgende parameters voor **[!UICONTROL Day CQ Mail Service]** met de details die op hun naam worden vermeld:

   * hostnaam SMTP-server: hostnaam e-mailserver
   * SMTP-serverpoort: e-mailserverpoort
   * SMTP-gebruiker: gebruikersnaam e-mailserver
   * SMTP-wachtwoord: wachtwoord e-mailserver
   ![chlimage_1-548](assets/chlimage_1-548.png)

1. Klik op **[!UICONTROL Opslaan]** of tik op Opslaan.

## Maximale gegevensgrootte configureren {#configure-maximum-data-size}

Wanneer u elementen downloadt van de koppeling die wordt gedeeld met de functie voor het delen van koppelingen, comprimeert AEM de volledige hiërarchie van elementen uit de opslagplaats en retourneert het element vervolgens in een ZIP-bestand. Bij gebrek aan beperkingen van de hoeveelheid gegevens die in een ZIP-bestand kan worden gecomprimeerd, worden enorme hoeveelheden gegevens gecomprimeerd, waardoor fouten in het geheugen in JVM worden veroorzaakt. Om het systeem van een potentiële ontkenning van de dienstaanval toe te schrijven aan deze situatie te beveiligen, vorm de maximumgrootte gebruikend de **[!UICONTROL Max (ongecomprimeerde)]** parameter van de Grootte van de Inhoud voor **[!UICONTROL Dag CQ DAM Adhoc Servlet]** van de Volmacht van het Aandeel van Activa in de Manager van de Configuratie. Als de niet-gecomprimeerde grootte van het element de geconfigureerde waarde overschrijdt, worden de verzoeken om het downloaden van het element afgewezen. De standaardwaarde is 100 MB.

1. Klik/Tik op het AEM-logo en ga vervolgens naar **[!UICONTROL Gereedschappen > Bewerkingen > Webconsole]**.
1. Zoek vanuit de webconsole de configuratie van de **[!UICONTROL Day CQ DAM Adhoc Asset Share Proxy Servlet]** .
1. Open de configuratie van de Proxy Server **[!UICONTROL van het Aandeel van het Middel van]** Dag CQ DAM Adhoc Middelen in geef wijze uit, en wijzig de waarde van de **[!UICONTROL Max (ongecomprimeerde)]** parameter van de Grootte van de Inhoud.

   ![chlimage_1-549](assets/chlimage_1-549.png)

1. Sla de wijzigingen op.

## Beste werkwijzen en probleemoplossing {#best-practices-and-troubleshooting}

* Elementmappen of verzamelingen die een witruimte in hun naam bevatten, worden mogelijk niet gedeeld.
* Als gebruikers de gedeelde elementen niet kunnen downloaden, vraagt u de AEM-beheerder na welke [downloadlimieten](#configure-maximum-data-size) gelden.
* Als u geen e-mail met koppelingen naar gedeelde elementen kunt verzenden of als de andere gebruikers uw e-mail niet kunnen ontvangen, raadpleegt u uw AEM-beheerder als de [e-mailservice](#configure-day-cq-mail-service) is geconfigureerd of niet.
* Als u geen elementen kunt delen via de functie voor het delen van koppelingen, controleert u of u de juiste machtigingen hebt. Zie [Elementen](#share-assets)delen.
