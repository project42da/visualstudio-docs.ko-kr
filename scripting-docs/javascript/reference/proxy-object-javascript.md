---
title: "프록시 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 2b89abee-04fa-47e6-9676-980016cff5f8
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 489d329528e88c27df03ca0e6d6d1608a39446e1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="proxy-object-javascript"></a>Proxy 개체(JavaScript)
개체에 대한 사용자 지정 동작을 활성화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
proxyObj = new Proxy(target, handler)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `target`  
 필수 요소. 프록시에서 가상화될 개체 또는 함수입니다.  
  
 `handler`  
 필수 요소. 사용자 지정 동작을 구현하는 메서드(트랩)가 있는 개체입니다.  
  
## <a name="remarks"></a>설명  
 `Proxy` 개체는 다른 개체에서 내부 하위 수준 작업을 가로채는 데 사용됩니다. Proxy 개체는 가로채기, 개체 가상화, 로깅/프로파일링 및 기타 목적으로 사용할 수 있습니다.  
  
 특정 작업에 대한 트랩이 프록시의 처리기에서 정의되지 않은 경우 작업은 대상에 전달됩니다.  
  
 처리기 개체는 다음 메서드(트랩)를 정의하여 사용자 지정 동작을 구현합니다. 여기에 있는 예제는 완전하지 않습니다. 처리기 메서드에서 조건부 기본 동작을 지원 하려면의 메서드를 사용 하 여 [반영 개체](../../javascript/reference/reflect-object-javascript.md)합니다.  
  
|처리기 메서드(트랩) 구문|사용 예제|  
|------------------------------------|-----------------------|  
|`apply: function(target, thisArg, args)`|함수 호출에 대한 트랩입니다.|  
|`construct: function(target, args)`|생성자에 대한 트랩입니다.|  
|`defineProperty: function(target, propertyName, descriptor)`|에 대 한 트랩 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)합니다.|  
|`deleteProperty: function(target, propertyName)`|`delete` 문에 대한 트랩입니다.|  
|`enumerate: function(target)`|에 대 한 트랩은 [>for..에서](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) 문, [Object.getOwnPropertySymbols](../../javascript/reference/object-getownpropertysymbols-function-javascript.md), [Object.keys](../../javascript/reference/object-keys-function-javascript.md) 함수 및 [JSON.stringify](../../javascript/reference/json-stringify-function-javascript.md)합니다.|  
|`get: function(target, propertyName, receiver)`|모든 트랩 [getter](../../javascript/creating-objects-javascript.md) 속성입니다.|  
|`getOwnPropertyDescriptor: function(target, propertyName)`|에 대 한 트랩 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)합니다.|  
|`getPrototypeOf: function(target)`|에 대 한 트랩 [Object.getPrototypeOf 함수](../../javascript/reference/object-getprototypeof-function-javascript.md)합니다.|  
|`has: function(target, propertyName)`|에 대 한 트랩은 `in` 연산자 [hasOwnProperty 메서드 (Object)](../../javascript/reference/hasownproperty-method-object-javascript.md), 및 기타 방법.|  
|`isExtensible: function(target)`|에 대 한 트랩 [Object.isExtensible 함수](../../javascript/reference/object-isextensible-function-javascript.md)합니다.|  
|`ownKeys: function(target)`|에 대 한 트랩 [Object.getOwnPropertyNames 함수](../../javascript/reference/object-getownpropertynames-function-javascript.md)합니다.|  
|`preventExtensions: function(target)`|에 대 한 트랩 [Object.preventExtensions 함수](../../javascript/reference/object-preventextensions-function-javascript.md)합니다.|  
|`set: function(target, propertyName, value, receiver)`|모든 트랩 [setter](../../javascript/creating-objects-javascript.md) 속성입니다.|  
|`setPrototypeOf: function(target, prototype)`|에 대 한 트랩 [Object.setPrototypeOf](../../javascript/reference/object-setprototypeof-function-javascript.md)합니다.|  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `get` 트랩을 사용하여 개체 리터럴에 대한 프록시를 만드는 방법을 보여줍니다.  
  
```JavaScript  
var target = {};  
var handler = {  
  get: function (receiver, name) {  
    // This example includes a template string.  
    return `Hello, ${name}!`;  
  }  
};  
  
var p = new Proxy(target, handler);  
console.log(p.world);  
  
// Output:  
// Hello, world!  
  
```  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `apply` 트랩을 사용하여 함수에 대한 프록시를 만드는 방법을 보여줍니다.  
  
```JavaScript  
var target = function () { return 'I am the target'; };  
var handler = {  
  // This example includes a rest parameter.  
  apply: function (receiver, ...args) {  
    return 'I am the proxy';  
  }  
};  
  
var p = new Proxy(target, handler);  
console.log(target()):  
console.log(p()):  
  
// Output:  
// I am the target  
// I am the proxy  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]