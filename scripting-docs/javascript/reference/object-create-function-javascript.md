---
title: "Object.create 함수 (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- create function [JavaScript]
- Object.create function [JavaScript]
ms.assetid: 0ad31f36-a9ee-444e-b0fe-c87843d03196
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f359908c5c836743e22390580f542df27d7b98e7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objectcreate-function-javascript"></a>Object.create 함수(JavaScript)
지정 된 프로토타입이 있고 선택적으로 지정 된 속성을 포함 하는 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
Object.create(prototype, descriptors)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `prototype`  
 필수 요소. 프로토타입을으로 사용할 개체입니다. `null`일 수 있습니다.  
  
 `descriptors`  
 선택 사항입니다. A [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 하나 이상의 속성 설명자를 포함 하는 개체입니다.  
  
 *데이터 속성*은 값을 가져오고 설정할 수 있는 속성입니다. 데이터 속성 설명자를 포함 한 `value` 특성을 더한 `writable`, `enumerable`, 및 `configurable` 특성입니다. 기본적으로 마지막 세 가지 특성이 지정 되지 않은 경우 `false`합니다. *접근자 속성* 될 때마다 값 검색 또는 설정 되는 사용자 제공 함수를 호출 합니다. 접근자 속성 설명자를 포함 한 `set` 특성은 `get` 특성 또는 둘 다 합니다. 자세한 내용은 참조 [Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 지정 된 내부 프로토타입을 않으며 있는 경우 지정 된 속성을 포함 하는 새 개체입니다.  
  
## <a name="exceptions"></a>예외  
 A `TypeError` 다음 조건 중 하나에 해당 하는 경우 예외가 throw 됩니다.  
  
-   `prototype` 인수는 개체가 아니며 `null`합니다.  
  
-   설명자는 `descriptors` 인수에는 `value` 또는 `writable` 특성이 있고는 `get` 또는 `set` 특성입니다.  
  
-   설명자는 `descriptors` 인수에는 `get` 또는 `set` 특성은 함수가 아니며입니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여이 함수를 사용할 수 있습니다는 `null``prototype` 프로토타입 체인을 중지 하려면 매개 변수입니다. 앞에서 만든 개체에는 프로토타입이 없는 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하 여 개체는 `null` 프로토타입 두 열거 가능한 속성을 추가 합니다.  
  
```JavaScript  
var newObj = Object.create(null, {  
            size: {  
                value: "large",  
                enumerable: true  
            },  
            shape: {  
                value: "round",  
                enumerable: true  
            }  
        });  
  
document.write(newObj.size + "<br/>");  
document.write(newObj.shape + "<br/>");  
document.write(Object.getPrototypeOf(newObj));  
  
// Output:  
// large  
// round  
// null  
  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 개체 개체와 동일한 내부 프로토타입을 가진 개체를 만듭니다. 리터럴 개체를 사용 하 여 만든 개체로 동일 프로토타입으로 있다는 것을 볼 수 있습니다. [Object.getPrototypeOf](../../javascript/reference/object-getprototypeof-function-javascript.md) 함수는 원래 개체의 프로토타입의 가져옵니다. 개체의 속성 설명자를 얻기 위해 사용할 수 있습니다 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)합니다.  
  
```JavaScript  
var firstLine = { x: undefined, y: undefined };  
  
var secondLine = Object.create(Object.prototype, {  
        x: {  
                value: undefined,   
                writable: true,   
                configurable: true,   
                enumerable: true  
            },  
            y: {  
                value: undefined,   
                writable: true,   
                configurable: true,   
                enumerable: true  
            }  
});  
  
document.write("first line prototype = " + Object.getPrototypeOf(firstLine));  
document.write("<br/>");  
document.write("second line prototype = " + Object.getPrototypeOf(secondLine));  
  
// Output:  
// first line prototype = [object Object]  
// second line prototype = [object Object]  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 도형 개체와 동일한 내부 프로토타입을 가진 개체를 만듭니다.  
  
```JavaScript  
  
// Create the shape object.  
var Shape = { twoDimensional: true, color: undefined, hasLineSegments: undefined };  
  
var Square = Object.create(Object.getPrototypeOf(Shape));  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Object.getPrototypeOf 함수](../../javascript/reference/object-getprototypeof-function-javascript.md)   
 [isPrototypeOf 메서드 (Object)](../../javascript/reference/isprototypeof-method-object-javascript.md)   
 [개체 만들기](../../javascript/creating-objects-javascript.md)