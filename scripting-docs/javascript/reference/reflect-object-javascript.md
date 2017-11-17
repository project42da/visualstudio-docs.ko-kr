---
title: "Reflect 개체 (JavaScript) | Microsoft Docs"
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
ms.assetid: 1df74f34-2eb4-42f1-a930-b943c86daa0e
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3574c54ee7ff69f56951cd7f4c9a93cac5275fc1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="reflect-object-javascript"></a>Reflect 개체(JavaScript)
가로챈 작업에서 사용할 메서드를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Reflect.[method]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `method`  
 필수 요소. `Reflect` 개체의 메서드 중 하나의 이름입니다.  
  
## <a name="remarks"></a>설명  
 Reflect 개체는 `new` 연산자로 인스턴스화할 수 없습니다.  
  
 메서드는 종종와 함께 사용 되어 반영 [프록시](../../javascript/reference/proxy-object-javascript.md) 코드에서 기본 동작을 구현 하지 않고 기본 동작으로 위임할 수 있기 때문에 있습니다.  
  
 Reflect는 각 프록시 트랩과 동일한 이름을 가진 정적 메서드를 제공합니다. 표에서 자세히 설명하지는 않습니다.  
  
|메서드|설명|  
|------------|-----------------|  
|`Reflect.apply(target, thisArg, args)`|비슷합니다는 [적용](../../javascript/reference/apply-method-function-javascript.md) 함수 개체의 메서드.|  
|`Reflect.construct(target, args)`|`new` 연산자에 해당하는 함수입니다.|  
|`Reflect.defineProperty(target, propertyName, descriptor)`|비슷한 [Object.defineProperty](../../javascript/reference/object-defineproperty-function-javascript.md)합니다. 호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.deleteProperty(target, propertyName)`|`delete` 문과 비슷합니다. 호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.enumerate(target)`|비슷한 [>for...에](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) 문, [Object.getOwnPropertySymbols](../../javascript/reference/object-getownpropertysymbols-function-javascript.md), [Object.keys](../../javascript/reference/object-keys-function-javascript.md) 함수 및 [JSON.stringify](../../javascript/reference/json-stringify-function-javascript.md)합니다.|  
|`Reflect.get(target, propertyName, receiver)`|에 대 한 해당 하는 함수 [getter](../../javascript/creating-objects-javascript.md) 속성입니다.|  
|`Reflect.getOwnPropertyDescriptor(target, propertyName)`|비슷한 [Object.getOwnPropertyDescriptor](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)합니다. 호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.getPrototypeOf(target)`|비슷한 [Object.getPrototypeOf](../../javascript/reference/object-getprototypeof-function-javascript.md)합니다.|  
|`Reflect.has(target, propertyName)`|비슷합니다는 `in` 연산자 [hasOwnProperty 메서드 (Object)](../../javascript/reference/hasownproperty-method-object-javascript.md), 및 기타 방법. 호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.isExtensible(target)`|비슷한 [Object.isExtensible](../../javascript/reference/object-isextensible-function-javascript.md)합니다.|  
|`Reflect.ownKeys(target)`|비슷한 [Object.getOwnPropertyNames](../../javascript/reference/object-getownpropertynames-function-javascript.md)합니다.|  
|`Reflect.preventExtensions(target)`|비슷한 [Object.preventExtensions](../../javascript/reference/object-preventextensions-function-javascript.md)합니다. 호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.set(target, propertyName, value, receiver)`|사용 하 여 비슷한 [setter](../../javascript/creating-objects-javascript.md) 속성입니다. 호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
|`Reflect.setPrototypeOf(target, prototype)`|비슷한 [Object.setPrototypeOf](../../javascript/reference/object-setprototypeof-function-javascript.md)합니다. 호출에 성공했는지 여부를 나타내는 부울 값을 반환합니다.|  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Reflect.get`을 사용하여 밑줄로 시작하는 속성에 대한 get 작업을 차단하는 프록시를 작성하는 방법을 보여 줍니다.  
  
```JavaScript  
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
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]