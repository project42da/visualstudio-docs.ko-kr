---
title: "toJSON 메서드(Date)(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toJSON 메서드"
ms.assetid: f91df030-e9c9-425e-8e6d-b46bdda66cb6
caps.latest.revision: 27
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 27
---
# toJSON 메서드(Date)(JavaScript)
[JSON.stringify](../../javascript/reference/json-stringify-function-javascript.md) 메서드에서 JSON\(JavaScript Object Notation\) serialization에 대한 개체 데이터의 변환을 허용하는 데 사용합니다.  
  
## 구문  
  
```  
  
objectname.toJSON()  
```  
  
## 매개 변수  
 `objectname`  
 필수 요소.  JSON serialization이 필요한 개체입니다.  
  
## 설명  
 `toJSON` 메서드는 `JSON.stringify` 함수에서 사용됩니다.  `JSON.stringify`는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 값을 JSON 텍스트로 serialize합니다.  `toJSON` 메서드를 `JSON.stringify`에 지정하면 `JSON.stringify`를 호출할 때 `toJSON` 메서드가 호출됩니다.  
  
 `toJSON` 메서드는 [Date](../../javascript/reference/date-object-javascript.md) [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체의 기본 제공 멤버입니다.  접미사 Z로 식별된 UTC 표준 시간대의 ISO 형식 날짜 문자열을 반환합니다.  
  
 `Date` 형식에 대한 `toJSON` 메서드를 재정의하거나 다른 개체 형식에 대해 `toJSON` 메서드를 정의하여 JSON serialization 전에 특정 개체 형식의 데이터를 변환할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `toJSON` 메서드를 사용하여 문자열 멤버 값을 대문자로 serialize합니다.  `JSON.stringify`를 호출하면 `toJSON` 메서드가 호출됩니다.  
  
```javascript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
contact.toJSON = function(key)  
 {  
    var replacement = new Object();  
    for (var val in this)  
    {  
        if (typeof (this[val]) === 'string')  
            replacement[val] = this[val].toUpperCase();  
        else  
            replacement[val] = this[val]  
    }  
    return replacement;  
};  
  
var jsonText = JSON.stringify(contact);  
  
/* The value of jsonText is:  
'{"firstname":"JESPER","surname":"AABERG","phone":["555-0100","555-0120"]}'  
*/  
```  
  
## 예제  
 다음 예제에서는 [Date](../../javascript/reference/date-object-javascript.md) 개체의 기본 제공 멤버인 `toJSON` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
var dt = new Date('8/24/2009');  
dt.setUTCHours(7, 30, 0);  
var jsonText = JSON.stringify(dt);  
  
/* The value of jsonText is:  
'"2009-08-24T07:30:00Z"'  
*/  
```  
  
## 요구 사항  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)] **적용 대상:** [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [JSON 개체](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md)   
 [JSON.stringify 함수](../../javascript/reference/json-stringify-function-javascript.md)   
 [JavaScript 메서드](../../javascript/reference/javascript-methods.md)