---
title: "Boolean 개체(JavaScript) | Microsoft Docs"
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
  - "boolean_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Boolean 데이터 형식, Boolean 개체"
  - "Boolean 개체"
ms.assetid: d67748f2-7bf5-4889-8269-e777616cc5f0
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# Boolean 개체(JavaScript)
새 부울 값을 만듭니다.  
  
## 구문  
  
```  
  
boolObj = new Boolean([boolValue])  
```  
  
## 매개 변수  
 `boolObj`  
 필수 요소.  `Boolean` 개체가 할당되는 변수 이름입니다.  
  
 `boolValue`  
 선택 사항입니다.  새 개체의 초기 부울 값입니다.  `boolvalue`가 생략되거나 `false`, 0, `null`, `NaN` 또는 빈 문자열이면 부울 개체의 초기 값은 `false`입니다.  그렇지 않으면 초기 값은 `true`입니다.  
  
## 설명  
 `Boolean` 개체는 부울 데이터 형식에 대한 래퍼입니다.  [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 부울 데이터 형식이 `Boolean` 개체로 변환될 때마다 암시적으로 `Boolean` 개체를 사용합니다.  
  
 `Boolean` 개체를 명시적으로 인스턴스화하는 경우는 거의 없습니다.  
  
## 속성  
 다음 표에서는 `Boolean` 개체의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------|--------|  
|[constructor 속성](../../javascript/reference/constructor-property-boolean.md)|부울을 만드는 함수를 지정합니다.|  
|[prototype 속성](../../javascript/reference/prototype-property-boolean.md)|부울의 프로토타입에 대한 참조를 반환합니다.|  
  
<a name="js56jsobjarraymeth"></a>   
## 메서드  
 다음 표에서는 `Boolean` 개체의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|---------|--------|  
|[toString 메서드](../../javascript/reference/tostring-method-boolean-1.md)|부울을 나타내는 문자열을 반환합니다.|  
|[valueOf 메서드](../../javascript/reference/valueof-method-boolean.md)|부울에 대한 참조를 가져옵니다.|  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]