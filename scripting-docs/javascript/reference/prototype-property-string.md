---
title: "prototype 속성 (String) | Microsoft Docs"
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
ms.assetid: 437ce478-9c45-45f7-8952-bd71856cfcd8
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df8c6abbd64fce9172d805c2e22dee51f4fbbee4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-string"></a>prototype 속성(String)
문자열의 클래스에 대 한 프로토타입의에 대 한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
string.prototype  
```  
  
## <a name="remarks"></a>설명  
 `string` 인수는 문자열의 이름입니다.  
  
 `prototype` 속성을 사용하여 개체 클래스에 기본 기능 집합을 제공합니다. 인스턴스의 새 개체는 해당 개체에 할당된 프로토타입의 동작을 "상속"합니다.  
  
 예를 들어, 메서드를 추가 하는 `String` 문자열의 마지막 요소의 값을 반환 하는 개체, 함수 선언에 추가 `String.prototype`, 한 다음 사용 합니다.  
  
```JavaScript  
function string_last( ){  
    return this.charAt(this.length - 1);  
}  
String.prototype.last = string_last;  
var myString = new String("every good boy does fine");  
document.write(myString.last());  
  
// Output:  
// e  
```  
  
 모든 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체는 `prototype` 속성은 읽기 전용입니다. 속성 및 메서드는 프로토타입에 추가할 수 있지만 개체에 다른 프로토타입을 할당할 수 있습니다. 그러나 사용자 정의 개체에는 새 프로토타입을 할당할 수 있습니다.  
  
 이 언어 참조의 각 내부 개체에 대 한 메서드 및 속성 목록이는 개체의 프로토타입의 일부를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]