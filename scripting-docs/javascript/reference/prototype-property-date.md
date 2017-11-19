---
title: "prototype 속성 (Date) | Microsoft Docs"
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
ms.assetid: 44f9c637-7da7-4833-906d-358506f32ced
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8c0b337964d2a2fe17a4e9a7906d81069470e61b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-date"></a>prototype 속성(Date)
날짜에 대 한 프로토타입의에 대 한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
date.prototype  
```  
  
## <a name="remarks"></a>설명  
 `date` 인수는 개체 이름입니다.  
  
 사용 하 여는 `prototype` 속성을 날짜에는 기본 기능 집합을 제공 합니다. 인스턴스의 새 개체는 해당 개체에 할당된 프로토타입의 동작을 "상속"합니다.  
  
 예를 들어 배열의 최대 요소 값을 반환하는 `Date` 개체에 메서드를 추가하려면 함수를 선언하고 `Date.prototype`에 추가한 다음 사용합니다.  
  
```JavaScript  
function max( ){  
    var max = new Date();  
    max.setFullYear(2200, 01, 01);  
    return max;  
}  
Date.prototype.maxDate = max;  
var myDate = new Date();  
  
if (myDate < myDate.maxDate())  
    document.write("today isn't the max");  
else if (myDate == myDate.maxDate())  
    document.write("today is the max");   
  
// Output:  
// today isn't the max  
  
```  
  
 모든 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체는 `prototype` 속성은 읽기 전용입니다. 속성 및 메서드는 프로토타입에 추가할 수 있지만 개체에 다른 프로토타입을 할당할 수 있습니다. 그러나 사용자 정의 개체에는 새 프로토타입을 할당할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]