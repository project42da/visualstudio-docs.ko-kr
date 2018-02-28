---
title: "prototype 속성 (Object) (JavaScript) | Microsoft Docs"
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
- Prototype
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- inheritance, objects
- Prototype property
ms.assetid: 9fc434a1-5995-4fcb-a4e8-00e7f615aaa2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a73d213b6b17f5046eb1f4c498aeb223f942f2d8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-object-javascript"></a>prototype 속성(Object)(JavaScript)
개체 클래스의 프로토타입에 대한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
objectName.prototype  
```  
  
## <a name="remarks"></a>설명  
 `objectName` 인수는 개체 이름입니다.  
  
 `prototype` 속성을 사용하여 개체 클래스에 기본 기능 집합을 제공합니다. 인스턴스의 새 개체는 해당 개체에 할당된 프로토타입의 동작을 "상속"합니다.  
  
 예를 들어 배열의 최대 요소 값을 반환하는 `Array` 개체에 메서드를 추가하려면 함수를 선언하고 `Array.prototype`에 추가한 다음 사용합니다.  
  
```JavaScript  
function array_max( ){  
    var i, max = this[0];  
    for (i = 1; i < this.length; i++)  
    {  
    if (max < this[i])  
    max = this[i];  
    }  
    return max;  
}  
Array.prototype.max = array_max;  
var myArray = new Array(7, 1, 3, 11, 25, 9  
);  
document.write(myArray.max());  
  
// Output:  
// 25  
  
```  
  
 모든 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체는 `prototype` 속성은 읽기 전용입니다. 속성 및 메서드는 프로토타입에 추가할 수 있지만 개체에 다른 프로토타입을 할당할 수 있습니다. 그러나 사용자 정의 개체에는 새 프로토타입을 할당할 수 있습니다.  
  
 이 언어 참조의 각 내부 개체에 대 한 메서드 및 속성 목록이는 개체의 프로토타입의 일부를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [constructor 속성(Object)](../../javascript/reference/constructor-property-object-javascript.md)