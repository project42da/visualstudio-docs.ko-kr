---
title: "prototype 속성 (Number) | Microsoft Docs"
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
ms.assetid: d5fb87af-fc3a-4469-8dde-d31daf654f94
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dba8b8886b4fdbc48a662796863b1dfca019aec
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-number"></a>prototype 속성(Number)
프로토타입에 대 수의 클래스에 대 한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
number.prototype  
```  
  
## <a name="remarks"></a>설명  
 `number` 인수는 숫자의 이름입니다.  
  
 `prototype` 속성을 사용하여 개체 클래스에 기본 기능 집합을 제공합니다. 인스턴스의 새 개체는 해당 개체에 할당된 프로토타입의 동작을 "상속"합니다.  
  
 예를 들어, 메서드를 추가 하는 `Number` (정수)의 숫자 자릿수를 반환 하는 개체, 함수 선언에 추가 `Number.prototype`, 한 다음 사용 합니다.  
  
```JavaScript  
function number_digits() {  
    var digits = 0;  
    var num = this;  
    while (num) >= 1) {  
        digits++;  
        num /= 10;  
    }  
    return digits;  
}  
  
Number.prototype.digits = number_digits;  
var myNumber = new Number(3456.789);  
document.write(myNumber.digits());  
// Output:  
// 4  
```  
  
 모든 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체는 `prototype` 속성은 읽기 전용입니다. 속성 및 메서드는 프로토타입에 추가할 수 있지만 개체에 다른 프로토타입을 할당할 수 있습니다. 그러나 사용자 정의 개체에는 새 프로토타입을 할당할 수 있습니다.  
  
 이 언어 참조의 각 내부 개체에 대 한 메서드 및 속성 목록이는 개체의 프로토타입의 일부를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]