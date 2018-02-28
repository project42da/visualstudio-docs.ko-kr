---
title: "hasOwnProperty 메서드 (Object) (JavaScript) | Microsoft Docs"
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
- hasOwnProperty
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- hasOwnProperty method
ms.assetid: 3eb69d69-486f-4792-9518-4452aef369ca
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 397b68fc87bf730886c928e099037ff0183a7f63
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="hasownproperty-method-object-javascript"></a>hasOwnProperty 메서드(Object)(JavaScript)
개체에 지정 된 이름 가진 속성이 있는지 여부를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.hasOwnProperty(proName)  
```  
  
## <a name="parameters"></a>매개 변수  
 `object`  
 필수 요소. 개체의 인스턴스입니다.  
  
 `proName`  
 필수 요소. 문자열 속성 이름의 값입니다.  
  
## <a name="remarks"></a>설명  
 `hasOwnProperty` 메서드 반환 `true` 경우 `object` 에 지정 된 이름의 속성이 `false` 그렇지 않은 경우. 이 메서드는 개체의 프로토타입 체인;의 속성을 확인 하지 않습니다. 속성은 개체 자체의 구성원 이어야 합니다.  
  
 이 속성 아래 및 Internet Explorer 8에 대 한 호스트 개체에서 지원 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 모든 `String` 개체 메서드를 분할 하는 공통 공유 합니다. 다음 코드에서는 **false** 및 **true**합니다.  
  
```JavaScript  
var s = new String("Sample");  
document.write(s.hasOwnProperty("split"));  
document.write("<br/>");  
document.write(String.prototype.hasOwnProperty("split"));  
  
// Output:  
// false  
// true  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [in 연산자](../../javascript/reference/in-operator-decrementjavascript.md)