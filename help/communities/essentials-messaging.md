---
title: Grondbeginselen van berichten
seo-title: Grondbeginselen van berichten
description: Overzicht van de component Messaging
seo-description: Overzicht van de component Messaging
uuid: 53711f4d-6bbc-4be9-aefe-4e75a81cd67f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: eb8fd2b3-0a31-425e-b0f1-38f09e1106df
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c

---


# Grondbeginselen van berichten {#messaging-essentials}

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
   <td> <strong>templates</strong></td> 
   <td>/libs/social/messaging/components/hbs/composemessage/composemessage.hbs</td> 
  </tr> 
  <tr> 
   <td><strong>css</strong></td> 
   <td>/libs/social/messaging/components/hbs/composemessage/clientlibs/composemessage.css</td> 
  </tr> 
  <tr> 
   <td><strong>eigenschappen</strong></td> 
   <td>zie <a href="configure-messaging.md">Bevestigen van Overseinen</a></td> 
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
   <td> <strong>templates</strong></td> 
   <td>/libs/social/messaging/components/hbs/messagebox/messagebox.hbs</td> 
  </tr> 
  <tr> 
   <td><strong>css</strong></td> 
   <td>/libs/social/messaging/components/hbs/messagebox/clientlibs/messagebox.css</td> 
  </tr> 
  <tr> 
   <td><strong>eigenschappen</strong></td> 
   <td>Zie <a href="configure-messaging.md">Berichten configureren</a></td> 
  </tr> 
  <tr> 
   <td><strong>beheerdersconfiguratie</strong></td> 
   <td><a href="messaging.md">Berichten configureren</a></td> 
  </tr> 
 </tbody> 
</table>

Zie ook Aanpassingen aan de [clientzijde](client-customize.md)

## Essentiële elementen voor server-side {#essentials-for-server-side}

* [Berichten configureren](configure-messaging.md)

* [Berichtenclient-API&#39;s](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/messaging/client/api/package-summary.html) voor SCF-componenten

* [Berichten-API&#39;s](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/messaging/api/package-summary.html) voor de service

* [Eindpunten van berichten](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/messaging/client/endpoints/package-summary.html)

* [Aanpassingen op de server](server-customize.md)

>[!CAUTION]
>
>De parameter van het Koord moet *not *contain een het slepen schuine streep &quot;/&quot;voor de volgende methodes MessageBuilder:
>
>* `setInboxPath`()
>* `setSentItemsPath`()
>
>
Bijvoorbeeld:
>
>
```>
>valid: mb.setInboxPath( "/mail/inbox" );
> not valid: mb.setInboxPath( "/mail/inbox/" );
>```>



### Community-site {#community-site}

Een structuur van de communautaire plaats, die gebruikend de tovenaar wordt gecreeerd, zal de overseineneigenschap omvatten wanneer geselecteerd. Zie de `User Management` instellingen van de [Community Sites Console](sites-console.md#user-management).

### Voorbeeldcode: Bericht ontvangen {#sample-code-message-received-notification}

De eigenschap van het Overseinen van het Sociale Berichten werpt gebeurtenissen voor verrichtingen, bijvoorbeeld `send`, `marking read`, `marking delete`. Deze gebeurtenissen kunnen worden afgevangen en er kunnen acties worden ondernomen op basis van de gegevens in de gebeurtenis.

Het volgende voorbeeld is van een gebeurtenishandler die luistert naar de `message sent` gebeurtenis en een e-mail verzendt naar alle berichtontvangers die de gebeurtenis gebruiken `Day CQ Mail Service`.

Om het server-zijsteekproefmanuscript te proberen, zult u een ontwikkelomgeving en de capaciteit nodig hebben om een bundel te bouwen OSGi.

1. Aanmelden als beheerder ` [CRXDE|Lite](http://localhost:4502/crx/de)`
1. Maak een `bundle node`insteekmodule `/apps/engage/install` met willekeurige namen, zoals

   * **[!UICONTROL Symbolische naam]**: com.connect.media.social.messaging.MessagingNotification
   * **[!UICONTROL Naam]**: Melding van zelfstudie aan de slag
   * **[!UICONTROL Omschrijving]**: een voorbeeldservice voor het verzenden van een e-mailbericht naar gebruikers wanneer zij een bericht ontvangen
   * **[!UICONTROL Pakket]**: `com.engage.media.social.messaging.notification`

1. Navigeren naar `/apps/engage/install/com.engage.media.social.messaging.MessagingNotification/src/main/java/com/engage/media/social/messaging/notification`

   1. De automatisch gemaakte `Activator.java` klasse verwijderen
   1. Klasse maken `MessageEventHandler.java`
   1. Kopieer/plak de onderstaande code in `MessageEventHandler.java`

1. Klik op Alles **[!UICONTROL opslaan]**
1. Navigeer naar alle instructies voor importeren `/apps/engage/install/com.engage.media.social.messaging.MessagingNotification/com.engage.media.social.messaging.MessagingNotification.bnd` en voeg deze toe, zoals in de `MessageEventHandler.java` code is geschreven.
1. De bundel maken
1. Ervoor zorgen dat `Day CQ Mail Service`OSGi-service is geconfigureerd
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

