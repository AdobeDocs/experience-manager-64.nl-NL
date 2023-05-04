---
title: Grondbeginselen van berichten
seo-title: Messaging Essentials
description: Overzicht van de component Messaging
seo-description: Messaging component overview
uuid: 53711f4d-6bbc-4be9-aefe-4e75a81cd67f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: eb8fd2b3-0a31-425e-b0f1-38f09e1106df
exl-id: c6ad3c2b-8776-4ec4-99da-ab73ecc61153
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 1%

---

# Grondbeginselen van berichten {#messaging-essentials}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Deze pagina documenteert de details van het werken met het gebruiken van de component van het Overseinen om een overseineneigenschap op een website te omvatten.

## Essentiële elementen voor client-kant {#essentials-for-client-side}

**Bericht samenstellen**

<table> 
 <tbody> 
  <tr> 
   <td> <strong>resourceType</strong></td> 
   <td><p>social/messaging/components/hbs/composemessement</p> </td> 
  </tr> 
  <tr> 
   <td> <a href="client-customize.md#clientlibs-for-scf"><strong>clientllibs</strong></a></td> 
   <td><p>cq.social.hbs.messaging</p> </td> 
  </tr> 
  <tr> 
   <td> <strong>sjablonen</strong></td> 
   <td>/libs/social/messaging/components/hbs/composemessage/composemessage.hbs</td> 
  </tr> 
  <tr> 
   <td><strong>css</strong></td> 
   <td>/libs/social/messaging/components/hbs/composemessage/clientlibs/composemessage.css</td> 
  </tr> 
  <tr> 
   <td><strong>eigenschappen</strong></td> 
   <td>zie <a href="configure-messaging.md">Berichten bevestigen</a></td> 
  </tr> 
  <tr> 
   <td><strong>beheerdersconfiguratie</strong></td> 
   <td><a href="messaging.md">Berichten configureren</a></td> 
  </tr> 
 </tbody> 
</table>

**Berichtlijst** (voor Postvak IN, Verzonden en Prullenbak)

<table> 
 <tbody> 
  <tr> 
   <td> <strong>resourceType</strong></td> 
   <td><p>social/messaging/components/hbs/messagebox</p> </td> 
  </tr> 
  <tr> 
   <td> <a href="client-customize.md#clientlibs-for-scf"><strong>clientllibs</strong></a></td> 
   <td><p>cq.social.hbs.messaging</p> </td> 
  </tr> 
  <tr> 
   <td> <strong>sjablonen</strong></td> 
   <td>/libs/social/messaging/components/hbs/messagebox/messagebox.hbs</td> 
  </tr> 
  <tr> 
   <td><strong>css</strong></td> 
   <td>/libs/social/messaging/components/hbs/messagebox/clientlibs/messagebox.css</td> 
  </tr> 
  <tr> 
   <td><strong>eigenschappen</strong></td> 
   <td>Zie <a href="configure-messaging.md">Berichten bevestigen</a></td> 
  </tr> 
  <tr> 
   <td><strong>beheerdersconfiguratie</strong></td> 
   <td><a href="messaging.md">Berichten configureren</a></td> 
  </tr> 
 </tbody> 
</table>

Zie ook [Aanpassingen aan de clientzijde](client-customize.md)

## Essentiële elementen voor server-side {#essentials-for-server-side}

* [Berichten configureren](configure-messaging.md)

* [Berichtenclient-API&#39;s](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/messaging/client/api/package-summary.html) voor SCF-componenten

* [Berichten-API&#39;s](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/messaging/api/package-summary.html) voor de dienst

* [Eindpunten van berichten](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/messaging/client/endpoints/package-summary.html)

* [Aanpassingen op de server](server-customize.md)

>[!CAUTION]
>
>De parameter van het Koord moet *not *contain een het slepen schuine streep &quot;/&quot;voor de volgende methodes MessageBuilder:
>
>* `setInboxPath`()
>* `setSentItemsPath`()
>
>Bijvoorbeeld:
>
>
```
>valid: mb.setInboxPath( "/mail/inbox" );
> not valid: mb.setInboxPath( "/mail/inbox/" );
>```

### Community-site {#community-site}

Een structuur van de communautaire plaats, die gebruikend de tovenaar wordt gecreeerd, zal de overseineneigenschap omvatten wanneer geselecteerd. Zie `User Management` instellingen van [Community Sites Console](sites-console.md#user-management).

### Voorbeeldcode: Bericht ontvangen {#sample-code-message-received-notification}

Met de functie Sociaal bericht worden bijvoorbeeld gebeurtenissen gegenereerd voor bewerkingen `send`, `marking read`, `marking delete`. Deze gebeurtenissen kunnen worden afgevangen en er kunnen acties worden ondernomen op basis van de gegevens in de gebeurtenis.

Het volgende voorbeeld is een gebeurtenishandler die luistert naar de gebeurtenis `message sent` en verzendt via de `Day CQ Mail Service`.

Om het server-zijsteekproefmanuscript te proberen, zult u een ontwikkelomgeving en de capaciteit nodig hebben om een bundel te bouwen OSGi.

1. Aanmelden als beheerder ` [CRXDE|Lite](http://localhost:4502/crx/de)`
1. Een `bundle node`in `/apps/engage/install` met willekeurige namen, zoals

   * **[!UICONTROL Symbolic Name]**: com.connect.media.social.messaging.MessagingNotification
   * **[!UICONTROL Name]**: Melding van zelfstudie aan de slag
   * **[!UICONTROL Description]**: een voorbeeldservice voor het verzenden van een e-mailbericht naar gebruikers wanneer zij een bericht ontvangen
   * **[!UICONTROL Package]**: `com.engage.media.social.messaging.notification`

1. Ga naar `/apps/engage/install/com.engage.media.social.messaging.MessagingNotification/src/main/java/com/engage/media/social/messaging/notification`

   1. Verwijder de `Activator.java` automatisch gemaakte klasse
   1. Klasse maken `MessageEventHandler.java`
   1. Kopieer/plak de onderstaande code in `MessageEventHandler.java`

1. Klik op **[!UICONTROL Save All]**
1. Navigeren naar `/apps/engage/install/com.engage.media.social.messaging.MessagingNotification/com.engage.media.social.messaging.MessagingNotification.bnd` en voeg alle instructies voor het importeren toe, zoals geschreven in het dialoogvenster `MessageEventHandler.java` code.
1. De bundel maken
1. Zorgen `Day CQ Mail Service`De dienst OSGi wordt gevormd
1. Aanmelden als een demogebruiker en e-mail naar een andere demogebruiker sturen
1. De ontvanger ontvangt een e-mail over een nieuw bericht

#### MessageEventHandler.java {#messageeventhandler-java}

```java
package com.engage.media.social.messaging.notification;

import org.apache.felix.scr.annotations.Component;
import org.apache.felix.scr.annotations.Properties;
import org.apache.felix.scr.annotations.Property;
import org.apache.felix.scr.annotations.Service;
import org.apache.felix.scr.annotations.Reference;
import org.apache.sling.api.resource.ResourceResolver;
import org.apache.sling.api.resource.ResourceResolverFactory;
import org.apache.sling.api.resource.Resource;
import org.apache.commons.mail.Email;
import org.apache.commons.mail.EmailException;
import org.apache.commons.mail.SimpleEmail;
import org.apache.commons.mail.HtmlEmail;
import java.util.List;
import org.osgi.service.event.Event;
import org.osgi.service.event.EventHandler;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import com.adobe.cq.social.messaging.api.Message;
import com.adobe.cq.social.messaging.api.MessagingEvent;
import com.day.cq.mailer.MessageGatewayService;
import com.day.cq.mailer.MessageGateway;

@Component(immediate=true)
@Service(EventHandler.class)
@Properties({
        @Property(name = "event.topics", value = "com/adobe/cq/social/message")
})
public class MessagingEventHandler implements EventHandler {
    private Logger logger = LoggerFactory.getLogger(MessagingEventHandler.class);

    @Reference
    ResourceResolverFactory resourceResolverFactory;

    @Reference
    private MessageGatewayService messageGatewayService;

    ResourceResolver resourceResolver=null;
    MessageGateway messageGateway=null;

    public void sendMail(String from, String to,String subject, String content){
        Email email = new SimpleEmail();
        messageGateway = messageGatewayService.getGateway(SimpleEmail.class);
        try {
         email.addTo(to);
            email.addReplyTo(from);
            email.setFrom(from);
            email.setMsg(content);
            email.setSubject(subject);
         messageGateway.send(email);
        } catch(EmailException ex) {
            logger.error("MessageNotificaiton : Error sending email : "+ex.getMessage());
        }
        logger.info("**** MessageNotification **** Mail sent to " + to);
    }

    public void handleEvent(Event event) {
        //Get Message Path and originator User's ID from event
        String messagePath = (String) event.getProperty("path");
        String senderId = (String) event.getProperty("userId");
        MessagingEvent.MessagingActions action = (MessagingEvent.MessagingActions) event.getProperty("action");
        try{
            if(MessagingEvent.MessagingActions.MessageSent.equals(action)){
                resourceResolver = resourceResolverFactory.getAdministrativeResourceResolver(null);

                //Read message
                Resource resource = resourceResolver.getResource(messagePath);
                Message msg = resource.adaptTo(Message.class);

                //Get list of recipient Ids from message
                //For Getting Started Tutorial, Id is same as email. If that is not the case in your site, 
                //an additional step is needed to retrieve the email for the Id
                List<String> reclist = msg.getRecipientIdList();
                for(int i=0;i<reclist.size();i++){
                    //Send Email using Mailing Service
                    sendMail("admin@cqadmin.qqq",reclist.get(i),"New message on Getting Started Tutorial", "Hi\nYou have received a new message from  " +  senderId + ". To read it, sign in to Getting Started Tutorial.\n\n-Engage Admin");
                }
            }
        } catch(Exception ex){
            logger.error("Error getting message info : " + ex.getMessage());
        } finally {
            resourceResolver.close();
        }

    }
}
```
