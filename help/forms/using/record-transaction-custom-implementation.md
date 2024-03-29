---
title: Een transactie opnemen voor aangepaste implementaties
seo-title: Record a transaction for custom implementations
description: Gebruik de API TransactionRecorder om handelingen op te nemen die niet automatisch als transacties worden beschouwd
seo-description: Use the TransactionRecorder API to record actions which are not accounted as transactions automatically
uuid: a22b1a0b-7553-4a17-8fb4-a3bee97b4a98
contentOwner: khsingh
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-manager
discoiquuid: 0d961630-573b-4c8e-902f-996f1d1265b6
exl-id: e97ecb77-96a0-44cf-8da9-1e85cc122011
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---

# Een transactie opnemen voor aangepaste implementaties {#record-a-transaction-for-custom-implementations}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Gebruik de API TransactionRecorder om handelingen op te nemen die niet automatisch als transacties worden beschouwd

U kunt een aangepaste code gebruiken om een PDF-formulier te verzenden, om de gebruikersinterface van de agent naar eindgebruikers te sturen voor een voorvertoning van een interactieve communicatie of om een formulier te verzenden met behulp van aangepaste methoden in plaats van verzendmethoden te gebruiken die bij AEM Forms worden geleverd. Alle eerder genoemde acties en aangepaste implementaties van AEM Forms API&#39;s worden niet als transacties beschouwd. AEM Forms beschikt over een API, [TransactionRecorder](https://helpx.adobe.com/experience-manager/6-4/forms/javadocs/com/adobe/aem/transaction/core/ITransactionRecorder.html), om dergelijke handelingen op te nemen als transacties.

Om een transactie op te nemen, schrijf [standaardslingerservlet](https://helpx.adobe.com/experience-manager/using/custom-sling-servlets.html) en roep het servlet van een cliënt aan om een transactie te registreren. U kunt servlet roepen gebruikend AJAX of een andere standaardmethode.

## Voorbeeld van code op de server {#sample-server-sided-code}

U kunt de onderstaande voorbeeldcode gebruiken om de API TransactionRecorder uit te voeren vanuit een JAVA-klasse met behulp van een aangepaste OSGi-bundel.

```java
import com.adobe.aem.transaction.core.ITransactionRecorder;
import com.adobe.aem.transaction.core.model.TransactionRecord;
import com.adobe.aem.transaction.core.exception.TransactionException;
import com.adobe.aem.transaction.core.FormsTransactionConstants;

@Reference
private ITransactionRecorder transactionRecorder;
 
doPost (SlingHttpServletRequest request, SlingHttpServletResponse response) {
    transactionRecorder.startContext();
    TransactionRecord txRecord = extractTxRecordFromRequest(request); //extract transaction relevant data from request
    try {
        bool success = doBillableWork();
        if (success) {
            transactionRecorder.recordTransaction(txRecord);
        }
    } catch (Exception e) {
        //exception handling
    } finally {
        transactionRecorder.endContext();
    }
}

//Here, it is assumed that txInfo is passed in Stringified json form in the ajax call (in data parameter). You can pass txInfo from client in any way that you find suitable.
private TransactionRecord extractTxRecordFromRequest(SlingHttpServletRequest request) {
    BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(request.getInputStream()));
    Map<String, Object> txDataMap = new HashMap<String, Object>();
    String txData = bufferedReader.readLine();
    JSONObject txInfo= new JSONObject(txData );
    try {
        String resourceType= txInfo.getString("resourceType");
        String transactionType = txInfo.getString("transactionType");
        Integer transactionCount = (Integer)txInfo.get("transactionCount");
        //Extract all the relevant tx record attributes similarly and pass them in Transaction Record constructor as per the java doc}
        return new TransactionRecord(transactionCount, transactionType, resourceType, ..);
    } catch (JSONException e) {
        //exception handling
    } finally {
        bufferedReader.close();
    }
}
```

## Voorbeeld van code aan clientzijde {#sample-client-side-code}

U kunt de onderstaande voorbeeldcode gebruiken om de servlet aan te roepen die de `TransactionRecorder`API.

```
$.ajax({
   type: 'POST',
   url: url, //servlet url
   contentType: 'application/json; UTF-8',
   data: JSON.stringify({transactionCount : 1, 
                        transactionType: "SUBMIT",
                        resourceType: "FORM",
                        resourceSubType: "ADAPTIVE-FORM"}),
   success: successHandler,
   error: faultHandler
})
```

## Verwante artikelen {#related-articles}

* [Overzicht van transactierapporten](/help/forms/using/transaction-reports-overview.md)
* [Transactierapporten weergeven en begrijpen](/help/forms/using/viewing-and-understanding-transaction-reports.md)
* [Transactierapporten Billable API&#39;s](/help/forms/using/transaction-reports-billable-apis.md)
