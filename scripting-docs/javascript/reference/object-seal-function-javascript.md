---
title: "Object.seal 함수(JavaScript) | Microsoft Docs"
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
  - "Object.seal 함수"
  - "seal 함수"
ms.assetid: e72c804a-4dab-4ec9-b9df-9c9c908aa12d
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# Object.seal 함수(JavaScript)
기존 속성의 특성 수정을 방지하고 새 속성의 추가를 방지합니다.  
  
## 구문  
  
```javascript  
Object.seal(object)  
```  
  
#### 매개 변수  
 `object`  
 필수 요소.  속성을 잠글 개체입니다.  
  
## 반환 값  
 함수에 전달된 개체입니다.  
  
## 예외  
 `object` 인수가 개체가 아닌 경우 `TypeError`예외가 throw됩니다.  
  
## 설명  
 `Object.seal` 함수는 다음 작업을 모두 수행합니다.  
  
-   새 속성을 추가할 수 없도록 개체를 확장할 수 없는 개체로 만듭니다.  
  
-   개체의 모든 속성에 대해 `configurable` 특성을 `false`로 설정합니다.  
  
 `configurable` 속성이 `false`이면 속성 특성을 변경할 수 없으며 속성을 삭제할 수 없습니다.  `configurable`이 `false`이고 `writable`이 `true`이면 `value` 및`writable` 특성을 변경할 수 있습니다.  
  
 `Object.seal` 함수는 `writable` 특성을 변경하지 않습니다.  
  
 속성 특성을 설정하는 방법에 대한 자세한 내용은 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)를 참조하세요.  속성의 특성을 가져오려면 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)를 사용할 수 있습니다.  
  
## 관련 함수  
 다음과 같은 관련 함수는 개체 특성의 수정을 방지합니다.  
  
|함수|개체가 확장할 수 없는 개체로 만들어졌는지 여부|`configurable`은 각 속성에 대해 `false`로 설정됩니다.|`writable`은 각 속성에 대해 `false`로 설정됩니다.|  
|--------|--------------------------------|----------------------------------------------|------------------------------------------|  
|[Object.preventExtensions](../../javascript/reference/object-preventextensions-function-javascript.md)|예|아니요|아니요|  
|`Object.seal`|예|예|아니요|  
|[Object.freeze](../../javascript/reference/object-freeze-function-javascript.md)|예|예|예|  
  
 다음 함수는 다음 표에 표시된 모든 조건이 true인 경우 `true`를 반환합니다.  
  
|함수|개체가 확장 가능합니까?|`configurable`이 모든 속성에 대해 `false`입니까?|`writable`이 모든 데이터 속성에 대해 `false`입니까?|  
|--------|-------------------|-------------------------------------------|-------------------------------------------|  
|[Object.isExtensible](../../javascript/reference/object-isextensible-function-javascript.md)|예|아니요|아니요|  
|[Object.isSealed](../../javascript/reference/object-issealed-function-javascript.md)|아니요|예|아니요|  
|[Object.isFrozen](../../javascript/reference/object-isfrozen-function-javascript.md)|아니요|예|예|  
  
## 예제  
 다음 예제에서는 `Object.seal` 함수의 사용법을 보여 줍니다.  
  
```javascript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
// Seal the object.  
Object.seal(obj);  
document.write(Object.isSealed(obj));  
document.write("<br/>");  
  
// Try to add a new property, and then verify that it is not added.   
obj.newProp = 50;  
document.write(obj.newProp);  
document.write("<br/>");  
  
// Try to delete a property, and then verify that it is still present.   
delete obj.length;  
document.write(obj.length);  
  
// Output:  
// true  
// undefined  
// 10  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [Object.preventExtensions 함수](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.freeze 함수](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isExtensible 함수](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.isSealed 함수](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.isFrozen 함수](../../javascript/reference/object-isfrozen-function-javascript.md)