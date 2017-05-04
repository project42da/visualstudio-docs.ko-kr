---
title: "Object.isFrozen 함수(JavaScript) | Microsoft Docs"
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
  - "isFrozen 함수[JavaScript]"
  - "Object.isFrozen 함수[JavaScript]"
ms.assetid: 6cf1bbc6-56e8-429b-8e2c-0024fa614acc
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# Object.isFrozen 함수(JavaScript)
기존 속성 특성 및 값을 개체에서 수정할 수 없고 개체에 새 속성을 추가할 수 없는 경우 `true`를 반환합니다.  
  
## 구문  
  
```javascript  
Object.isFrozen(object)  
```  
  
#### 매개 변수  
 `object`  
 필수 요소.  테스트할 개체입니다.  
  
## 반환 값  
 다음 항목이 모두 true인 경우 `true`를 반환합니다.  
  
-   새 속성을 개체에 추가할 수 없음을 나타내는 확장할 수 없는 개체입니다.  
  
-   `configurable` 특성이 기존의 모든 속성에 대해 `false`입니다.  
  
-   `writable` 특성이 기존의 모든 데이터 속성에 대해 `false`입니다.  
  
 개체에 기존 속성이 없는 경우 개체가 확장할 수 없는 개체이면 이 함수가 `true`를 반환합니다.  
  
## 예외  
 `object` 인수가 개체가 아닌 경우 `TypeError`예외가 throw됩니다.  
  
## 설명  
 속성의 `configurable` 특성이 `false`이면 속성 특성을 변경할 수 없고 속성을 삭제할 수 없습니다.  `false`가 `writable`이면 데이터 속성 값을 변경할 수 없습니다.  `configurable`이 `false`이고 `writable`이 `true`이면 `value` 및`writable` 특성을 변경할 수 있습니다.  
  
 속성 특성을 설정하는 방법에 대한 자세한 내용은 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)를 참조하세요.  속성의 특성을 가져오려면 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)를 사용할 수 있습니다.  
  
## 관련 함수  
 다음과 같은 관련 함수는 개체 특성의 수정을 방지합니다.  
  
|함수|개체가 확장할 수 없는 개체로 만들어졌는지 여부|`configurable`은 각 속성에 대해 `false`로 설정됩니다.|`writable`은 각 속성에 대해 `false`로 설정됩니다.|  
|--------|--------------------------------|----------------------------------------------|------------------------------------------|  
|[Object.preventExtensions](../../javascript/reference/object-preventextensions-function-javascript.md)|예|아니요|아니요|  
|[Object.seal](../../javascript/reference/object-seal-function-javascript.md)|예|예|아니요|  
|[Object.freeze](../../javascript/reference/object-freeze-function-javascript.md)|예|예|예|  
  
 다음 함수는 다음 표에 표시된 모든 조건이 true인 경우 `true`를 반환합니다.  
  
|함수|개체가 확장 가능합니까?|`configurable`이 모든 속성에 대해 `false`입니까?|`writable`이 모든 데이터 속성에 대해 `false`입니까?|  
|--------|-------------------|-------------------------------------------|-------------------------------------------|  
|[Object.isExtensible](../../javascript/reference/object-isextensible-function-javascript.md)|예|아니요|아니요|  
|[Object.isSealed](../../javascript/reference/object-issealed-function-javascript.md)|아니요|예|아니요|  
|`Object.isFrozen`|아니요|예|예|  
  
## 예제  
 다음 예제에서는 `Object.isFrozen` 함수의 사용법을 보여 줍니다.  
  
```javascript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Freeze the object, and verify that it is frozen.  
Object.freeze(obj);  
document.write(obj.isFrozen());  
  
// Try to add a new property, and then verify that it is not added.   
obj.newProp = 50;  
document.write (obj.newProp);  
document.write ("<br/>");  
  
// Try to delete a property, and then verify that it is still present.  
delete obj.length;  
document.write (obj.length);  
document.write ("<br/> ");  
  
// Try to change a property value, and then verify that it is not changed.  
obj.pasta = "linguini";  
document.write (obj.pasta);  
  
// Output:  
// true  
// undefined  
// 10  
// spaghetti  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 참고 항목  
 [Object.preventExtensions 함수](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.seal 함수](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.freeze 함수](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isExtensible 함수](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.isSealed 함수](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)   
 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)   
 [Object.getOwnPropertyNames 함수](../../javascript/reference/object-getownpropertynames-function-javascript.md)