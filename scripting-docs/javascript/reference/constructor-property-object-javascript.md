---
title: "constructor 속성 (Object) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: constructor
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: constructor property
ms.assetid: 6f5d0e9d-e85f-4fde-b558-744510483d69
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 569dab69906aa167ef486923bd7ceb7455ac243e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="constructor-property-object-javascript"></a>constructor 속성(Object)(JavaScript)
개체를 만드는 함수를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.constructor  
```  
  
## <a name="remarks"></a>설명  
 필요한 `object` 개체 또는 함수의 이름입니다.  
  
 `constructor` 속성은 프로토타입이 있는 모든 개체의 프로토타입 멤버입니다. 여기에 모든 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 제외한 개체는 `Global` 및 `Math` 개체입니다. `constructor` 속성은 해당 특정 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성자 속성의 사용을 보여 줍니다.  
  
```JavaScript  
// A constructor function.  
function MyObj() {  
    this.number = 1;  
}  
  
var x = new String("Hi");  
  
if (x.constructor == String)  
    document.write("Object is a String.");  
document.write ("<br />");  
  
var y = new MyObj;  
if (y.constructor == MyObj)  
    document.write("Object constructor is MyObj.");  
  
// Output:  
// Object is a String.  
// Object constructor is MyObj.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [prototype 속성(Object)](../../javascript/reference/prototype-property-object-javascript.md)