---
title: "Object.preventExtensions 함수(JavaScript) | Microsoft Docs"
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
  - "Object.preventExtensions 함수[JavaScript]"
  - "preventExtensions 함수[JavaScript]"
  - "새 속성 방지[JavaScript]"
  - "속성[JavaScript], 새 속성 방지"
ms.assetid: e6b48197-2374-4437-a9fe-519dd45a2077
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# Object.preventExtensions 함수(JavaScript)
개체에 대한 새 속성 추가를 방지합니다.  
  
## 구문  
  
```javascript  
Object.preventExtensions(object)  
```  
  
#### 매개 변수  
 `object`  
 필수 요소.  확장 불가능으로 설정할 개체입니다.  
  
## 반환 값  
 함수에 전달된 개체입니다.  
  
## 예외  
 `object` 인수가 개체가 아닌 경우 `TypeError`예외가 throw됩니다.  
  
## 설명  
 `Object.preventExtensions` 함수는 개체를 확장 불가능으로 설정하므로 새로 명명된 속성을 추가할 수 없습니다.  확장 불가능으로 설정된 개체를 다시 확장 가능으로 설정할 수는 없습니다.  
  
 속성 특성을 설정하는 방법에 대한 자세한 내용은 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)를 참조하세요.  
  
## 관련 함수  
 다음과 같은 관련 함수는 개체 특성의 수정을 방지합니다.  
  
|함수|개체가 확장할 수 없는 개체로 만들어졌는지 여부|`configurable`은 각 속성에 대해 `false`로 설정됩니다.|`writable`은 각 속성에 대해 `false`로 설정됩니다.|  
|--------|--------------------------------|----------------------------------------------|------------------------------------------|  
|`Object.preventExtensions`|예|아니요|아니요|  
|[Object.seal](../../javascript/reference/object-seal-function-javascript.md)|예|예|아니요|  
|[Object.freeze](../../javascript/reference/object-freeze-function-javascript.md)|예|예|예|  
  
 다음 함수는 다음 표에 표시된 모든 조건이 true인 경우 `true`를 반환합니다.  
  
|함수|개체가 확장 가능합니까?|`configurable`이 모든 속성에 대해 `false`입니까?|`writable`이 모든 데이터 속성에 대해 `false`입니까?|  
|--------|-------------------|-------------------------------------------|-------------------------------------------|  
|[Object.isExtensible](../../javascript/reference/object-isextensible-function-javascript.md)|예|아니요|아니요|  
|[Object.isSealed](../../javascript/reference/object-issealed-function-javascript.md)|아니요|예|아니요|  
|[Object.isFrozen](../../javascript/reference/object-isfrozen-function-javascript.md)|아니요|예|예|  
  
## 예제  
 다음 예제에서는 `Object.preventExtensions` 함수의 사용법을 보여 줍니다.  
  
```javascript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Make the object non-extensible.  
Object.preventExtensions(obj);  
document.write(Object.isExtensible(obj));  
document.write("<br/>");  
  
// Try to add a new property, and then verify that it is not added.  
obj.newProp = 50;  
document.write(obj.newProp);  
  
// Output:  
// false  
// undefined  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [Object.seal 함수](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.freeze 함수](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isExtensible 함수](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.isSealed 함수](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.isFrozen 함수](../../javascript/reference/object-isfrozen-function-javascript.md)