---
title: "Reflect 개체(JavaScript) | Microsoft Docs"
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
ms.assetid: 1df74f34-2eb4-42f1-a930-b943c86daa0e
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# Reflect 개체(JavaScript)
가로챈 작업에서 사용할 메서드를 제공합니다.  
  
## 구문  
  
```  
Reflect.[method]  
```  
  
#### 매개 변수  
 `method`  
 필수 요소.  `Reflect` 개체의 메서드 중 하나의 이름입니다.  
  
## 설명  
 Reflect 개체는 `new` 연산자로 인스턴스화할 수 없습니다.  
  
 Reflect 메서드는 코드에서 기본 동작을 구현하지 않고 기본 동작으로 위임할 수 있게 하므로 [프록시](../../javascript/reference/proxy-object-javascript.md)와 함께 사용되는 경우가 많습니다.  
  
 Reflect는 각 프록시 트랩과 동일한 이름을 가진 정적 메서드를 제공합니다.  표에서 자세히 설명하지는 않습니다.  
  
|메서드|설명|  
|---------|--------|  
|`Reflect.apply(target, thisArg, args)`|Function 개체의 [apply](../../javascript/reference/apply-method-function-javascript.md) 메서드와 비슷합니다.|  
|`Reflect.construct(target, args)`|`new` 연산자에 해당하는 함수입니다.|  
|`Reflect.defineProperty(target, propertyName, descriptor)`|[Object.defineProperty](../../javascript/reference/object-defineproperty-function-javascript.md)와 비슷합니다.  호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.deleteProperty(target, propertyName)`|`delete` 문과 비슷합니다.  호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.enumerate(target)`|[for…in](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) 문, [Object.getOwnPropertySymbols](../../javascript/reference/object-getownpropertysymbols-function-javascript.md), [Object.keys](../../javascript/reference/object-keys-function-javascript.md) 함수 및 [JSON.stringify](../../javascript/reference/json-stringify-function-javascript.md)와 비슷합니다.|  
|`Reflect.get(target, propertyName, receiver)`|[getter](../../javascript/creating-objects-javascript.md) 속성에 해당하는 함수입니다.|  
|`Reflect.getOwnPropertyDescriptor(target, propertyName)`|[Object.getOwnPropertyDescriptor](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)와 비슷합니다.  호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.getPrototypeOf(target)`|[Object.getPrototypeOf](../../javascript/reference/object-getprototypeof-function-javascript.md)와 비슷합니다.|  
|`Reflect.has(target, propertyName)`|`in` 연산자, [hasOwnProperty 메서드\(Object\)](../../javascript/reference/hasownproperty-method-object-javascript.md) 및 기타 메서드와 비슷합니다.  호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.isExtensible(target)`|[Object.isExtensible](../../javascript/reference/object-isextensible-function-javascript.md)과 비슷합니다.|  
|`Reflect.ownKeys(target)`|[Object.getOwnPropertyNames](../../javascript/reference/object-getownpropertynames-function-javascript.md)와 비슷합니다.|  
|`Reflect.preventExtensions(target)`|[Object.preventExtensions](../../javascript/reference/object-preventextensions-function-javascript.md)와 비슷합니다.  호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.set(target, propertyName, value, receiver)`|[setter](../../javascript/creating-objects-javascript.md) 속성 사용과 비슷합니다.  호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.setPrototypeOf(target, prototype)`|[Object.setPrototypeOf](../../javascript/reference/object-setprototypeof-function-javascript.md)와 비슷합니다.  호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
  
## 예제  
 다음 코드 예제에서는 `Reflect.get`을 사용하여 밑줄로 시작하는 속성에 대한 get 작업을 차단하는 프록시를 작성하는 방법을 보여 줍니다.  
  
```javascript  
var p = new Proxy({}, {  
    get(k, t, r) {  
        // return undefined if key begins with underscore  
        if(k[0] === '_') return undefined;  
  
       // otherwise do default behavior  
       return Reflect.get(k, t, r);  
    }  
});  
  
p._foo = 1;  
console.log(p._foo);  
  
p.foo = 1;  
console.log(p.foo);  
  
// Output:  
// undefined  
// 1  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]