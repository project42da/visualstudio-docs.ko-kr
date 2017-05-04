---
title: "propertyIsEnumerable 메서드(Object)(JavaScript) | Microsoft Docs"
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
  - "propertyIsEnumerable"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "propertyIsEnumerable 속성"
ms.assetid: d90c7c2e-ea23-4710-a957-9aefbbd1f68b
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# propertyIsEnumerable 메서드(Object)(JavaScript)
지정한 속성이 열거 가능한지 여부를 확인합니다.  
  
## 구문  
  
```  
  
object. propertyIsEnumerable(proName)  
```  
  
## 매개 변수  
 `object`  
 필수 요소.  개체의 인스턴스입니다.  
  
 `proName`  
 필수 요소.  속성 이름의 문자열 값입니다.  
  
## 설명  
 `propertyIsEnumerable` 메서드는 `proName`이 `object`에 있고 `For` 루프를 사용하여 열거할 수 있는 경우 `true`를 반환합니다.  `propertyIsEnumerable` 메서드는 `object`에 지정된 이름의 속성이 없거나 지정한 속성을 열거할 수 없는 경우 `false`를 반환합니다.  일반적으로 미리 정의된 속성은 열거할 수 없지만 사용자 정의 속성은 항상 열거할 수 있습니다.  
  
 `propertyIsEnumerable` 메서드는 프로토타입 체인에 있는 개체를 고려하지 않습니다.  
  
## 예제  
  
```javascript  
var a = new Array("apple", "banana", "cactus");  
document.write(a.propertyIsEnumerable(1));  
  
// Output: true  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [prototype 속성\(Object\)](../../javascript/reference/prototype-property-object-javascript.md)