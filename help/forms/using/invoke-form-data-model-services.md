---
title: API om de service voor formuliergegevensmodellen aan te roepen vanuit adaptieve formulieren
seo-title: API to invoke form data model service from adaptive forms
description: Verklaart invokeWebServices API die u kunt gebruiken om Webdiensten aan te halen die in WSDL van binnen een adaptief vormgebied worden geschreven.
seo-description: Explains the invokeWebServices API that you can use to invoke web services written in WSDL from within an adaptive form field.
uuid: 40561086-e69d-4e6a-9543-1eb2f54cd836
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: aa3e50f1-8f5a-489d-a42e-a928e437ab79
feature: Adaptive Forms
exl-id: 0653b0e4-a697-472a-8093-5ed48ede3c75
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# API om de service voor formuliergegevensmodellen aan te roepen vanuit adaptieve formulieren {#api-to-invoke-form-data-model-service-from-adaptive-forms}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

## Overzicht {#overview}

Met AEM Forms kunnen auteurs van formulieren de invulervaring van formulieren verder vereenvoudigen en verbeteren door services aan te roepen die vanuit een adaptief formulierveld zijn geconfigureerd in een formuliergegevensmodel. Als u een gegevensmodelservice wilt aanroepen, kunt u een regel maken in de visuele editor of een JavaScript opgeven met de `guidelib.dataIntegrationUtils.executeOperation` API in de code-editor van de [regeleditor](/help/forms/using/rule-editor.md).

Dit document is vooral bedoeld voor het schrijven van een JavaScript met het `guidelib.dataIntegrationUtils.executeOperation` API om de service aan te roepen.

## De API gebruiken {#using-the-api}

De `guidelib.dataIntegrationUtils.executeOperation` API roept een service aan vanuit een adaptief formulierveld. De API-syntaxis ziet er als volgt uit:

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

## Voorbeeldscript om een service aan te roepen {#sample-script-to-invoke-a-service}

In het volgende voorbeeldscript wordt het `guidelib.dataIntegrationUtils.executeOperation` API om de `getAccountById` de dienstverrichting die in `employeeAccount` formuliergegevensmodel.

De `getAccountById` de bewerking neemt de waarde in de `employeeID` formulierveld als invoer voor de `empId` argument en retourneert werknemersnaam, accountnummer en rekeningsaldo voor de corresponderende werknemer. De uitvoerwaarden worden ingevuld in de opgegeven formuliervelden. De waarde in `name` argument is ingevuld in het dialoogvenster `fullName` formulierelement en -waarde voor `accountNumber` argument in `account` formulierelement.

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
