---
title: "in 연산자(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "in_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "in 연산자"
ms.assetid: dcd8f901-96b8-4c91-848b-b1ec0ab1c11c
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# in 연산자(JavaScript)
개체에 속성이 존재하는지 여부를 테스트합니다.  
  
## 구문  
  
```  
  
result = property in object  
```  
  
## 매개 변수  
 `result`  
 필수 요소.  임의의 변수입니다.  
  
 `property`  
 필수 요소.  문자열 식으로 계산되는 식입니다.  
  
 `object`  
 필수 요소.  임의 개체입니다.  
  
## 설명  
 `in` 연산자는 개체에 `property`라는 속성이 있는지 여부를 확인합니다.  또한 속성이 개체의 프로토타입 체인의 일부인지도 확인합니다.  개체 프로토타입에 대한 자세한 내용은 [프로토타입 및 프로토타입 상속](../../javascript/advanced/prototypes-and-prototype-inheritance.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `in` 연산자를 사용하는 방법을 보여 줍니다.  
  
```javascript  
// Create an object that has some properties.  
var myObject = new Object();  
myObject.name = "James";  
myObject.age = "22";  
myObject.phone = "555 0234";  
  
if ("phone" in myObject)  
   document.write ("property is present");  
else  
   document.write ("property is not present");  
  
// Output: property is present  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)