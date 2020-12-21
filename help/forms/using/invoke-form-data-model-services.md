---
title: API om de service voor formuliergegevensmodellen aan te roepen vanuit adaptieve formulieren
seo-title: API om de service voor formuliergegevensmodellen aan te roepen vanuit adaptieve formulieren
description: 'Verklaart invokeWebServices API die u kunt gebruiken om Webdiensten aan te halen die in WSDL van binnen een adaptief vormgebied worden geschreven. '
seo-description: 'Verklaart invokeWebServices API die u kunt gebruiken om Webdiensten aan te halen die in WSDL van binnen een adaptief vormgebied worden geschreven. '
uuid: 40561086-e69d-4e6a-9543-1eb2f54cd836
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: aa3e50f1-8f5a-489d-a42e-a928e437ab79
translation-type: tm+mt
source-git-commit: 13d364ec820b48fb8b80da2ffd30faeeb7813a28
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 1%

---


# API om formuliergegevensmodelservice aan te roepen vanuit adaptieve formulieren {#api-to-invoke-form-data-model-service-from-adaptive-forms}

## Overzicht {#overview}

Met AEM Forms kunnen auteurs van formulieren de invulervaring van formulieren verder vereenvoudigen en verbeteren door services aan te roepen die vanuit een adaptief formulierveld zijn geconfigureerd in een formuliergegevensmodel. Om een dienst van het gegevensmodel aan te halen, kunt u of een regel in de visuele redacteur tot stand brengen of een JavaScript specificeren gebruikend `guidelib.dataIntegrationUtils.executeOperation` API in de coderedacteur van [rule redacteur](/help/forms/using/rule-editor.md).

Dit document is gericht op het schrijven van een JavaScript met de `guidelib.dataIntegrationUtils.executeOperation`-API om een service aan te roepen.

## API {#using-the-api} gebruiken

De `guidelib.dataIntegrationUtils.executeOperation`-API roept een service aan vanuit een adaptief formulierveld. De API-syntaxis ziet er als volgt uit:

```
guidelib.dataIntegrationUtils.executeOperation(operationInfo, inputs, outputs)
```

De API vereist de volgende parameters.

| Parameter | Beschrijving |
|---|---|
| `operationInfo` | Structuur voor het opgeven van de modelidentificatie, de bewerkingstitel en de naam van de bewerking van het formulier |
| `inputs` | Structuur om formulierobjecten op te geven waarvan de waarden worden ingevoerd voor de servicebewerking |
| `outputs` | Structuur voor het opgeven van formulierobjecten die worden gevuld met de waarden die door de servicebewerking worden geretourneerd |

De structuur van de `guidelib.dataIntegrationUtils.executeOperation` API specificeert details over de de dienstverrichting. De syntaxis van de structuur is als volgt.

```
var operationInfo = {
formDataModelId,
operationTitle,
operationName
};
var inputs = {
inputField1,
inputFieldN
};
var outputs = {
outputField1,
outputFieldN
}
```

De API-structuur geeft de volgende details over de servicebewerking op.

<table> 
 <tbody> 
  <tr> 
   <th>Parameter</th> 
   <th>Beschrijving</th> 
  </tr> 
  <tr> 
   <td><code>forDataModelId</code></td> 
   <td>Geef het pad van de gegevensopslagruimte naar het formuliergegevensmodel op, inclusief de naam ervan</td> 
  </tr> 
  <tr> 
   <td><code>operationName</code></td> 
   <td>Geef de naam op van de uit te voeren servicebewerking</td> 
  </tr> 
  <tr> 
   <td><code>input</code></td> 
   <td>Een of meer formulierobjecten toewijzen aan de invoerargumenten voor de servicebewerking</td> 
  </tr> 
  <tr> 
   <td>Uitvoer</td> 
   <td>Een of meer formulierobjecten toewijzen aan uitvoerwaarden van de servicebewerking om formuliervelden te vullen<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Voorbeeldscript om de service {#sample-script-to-invoke-a-service} aan te roepen

In het volgende voorbeeldscript wordt de `guidelib.dataIntegrationUtils.executeOperation`-API gebruikt om de `getAccountById`-servicebewerking aan te roepen die in het formuliergegevensmodel `employeeAccount` is geconfigureerd.

De bewerking `getAccountById` neemt de waarde in het formulierveld `employeeID` als invoer voor het argument `empId` en retourneert de werknemernaam, het accountnummer en het rekeningssaldo voor de corresponderende employee. De uitvoerwaarden worden ingevuld in de opgegeven formuliervelden. De waarde in het argument `name` wordt bijvoorbeeld ingevuld in het formulierelement `fullName` en de waarde voor het argument `accountNumber` in het formulierelement `account`.

```
var operationInfo = {
"formDataModelId": "/content/dam/formsanddocuments-fdm/employeeAccount",
"operationName": "getAccountDetails"
};
var inputs = {
"empid" : employeeID
};
var outputs = {
"name" : fullName,
"accountNumber" : account,
"balance" : balance
};
guidelib.dataIntegrationUtils.executeOperation(operationInfo, inputs, outputs);
```

