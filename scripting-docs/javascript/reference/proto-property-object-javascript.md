---
title: "__proto__ 속성 (Object) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __proto__
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 97c3f84d-125e-4905-b921-b021264964ee
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e38669c400acba6f4ed3c4ee3fb5836c31b1bc00
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="proto-property-object-javascript"></a>__proto__ 속성 (Object) (JavaScript)
지정된 된 개체의 내부 프로토타입에 대 한 참조를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
object.__proto__  
```  
  
#### <a name="parameters"></a>매개 변수  
 `object`  
 필수 요소. 프로토타입을 설정 하는 개체입니다.  
  
## <a name="remarks"></a>설명  
 `__proto__` 개체의 프로토타입을 설정 하 여 속성을 사용할 수 있습니다.  
  
 개체 또는 함수의 모든 메서드와 함께 새 프로토타입의 프로토타입 체인의 모든 속성과 메서드는 새 프로토타입의 속성을 상속합니다. 개체 수만 단일 프로토타입이 있어야 (하지 프로토타입 체인에 상속 된 프로토타입을 포함), 따라서 호출 하는 경우는 `__proto__` 속성을 이전 프로토타입을 대체 합니다.  
  
 프로토타입에 확장 가능한 개체에 대해서만 설정할 수 있습니다. 자세한 내용은 참조 하십시오. [Object.preventExtensions 함수](../../javascript/reference/object-preventextensions-function-javascript.md)합니다.  
  
> [!NOTE]
>  `__proto__` 속성 이름 시작 되 고 두 개의 밑줄로 끝나는 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 개체의 프로토타입을 설정하는 방법을 보여 줍니다.  
  
```JavaScript  
function Rectangle() {  
}  
  
var rec = new Rectangle();  
  
if (console && console.log) {  
    console.log(rec.__proto__ === Rectangle.prototype);  // Returns true  
    rec.__proto__ = Object.prototype;  
    console.log(rec.__proto__ === Rectangle.prototype);  // Returns false  
}  
```  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 프로토타입에 속성을 추가하여 개체에 속성을 추가하는 방법을 보여 줍니다.  
  
```JavaScript  
var proto = { y: 2 };  
  
var obj = { x: 10 };  
obj.__proto__ = proto;  
  
proto.y = 20;  
proto.z = 40;  
  
if (console && console.log) {  
    console.log(obj.x === 10);  // Returns true  
    console.log(obj.y === 20);  // Returns true  
    console.log(obj.z === 40);  // Returns true  
}  
```  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 새 프로토타입을 설정하여 `String` 개체에 속성을 추가합니다.  
  
```JavaScript  
var stringProp = { desc: "description" };  
  
String.__proto__ = stringProp;  
var s1 = "333";  
var s2 = new String("333");  
  
if (console && console.log) {  
  
    console.log(String.desc === "description"); // Returns true  
    console.log(s1.desc === "description");     // Returns false  
    console.log(s2.desc === "description");     // Returns false  
  
    s1.__proto__ = String;  // Can't be set.  
    s2.__proto__ = String;  
  
    console.log(s1.desc === "description"); // Returns false  
    console.log(s2.desc === "description"); // Returns true  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [프로토타입 및 프로토타입 상속](../../javascript/advanced/prototypes-and-prototype-inheritance.md)