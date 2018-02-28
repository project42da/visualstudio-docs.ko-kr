---
title: "propertyIsEnumerable 메서드 (Object) (JavaScript) | Microsoft Docs"
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
- propertyIsEnumerable
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- propertyIsEnumerable property
ms.assetid: d90c7c2e-ea23-4710-a957-9aefbbd1f68b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5664732db6a311586f11eb13eee4407fdf81410f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="propertyisenumerable-method-object-javascript"></a>propertyIsEnumerable 메서드(Object)(JavaScript)
지정된 된 속성의 열거 가능한 지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object. propertyIsEnumerable(proName)  
```  
  
## <a name="parameters"></a>매개 변수  
 `object`  
 필수 요소. 개체의 인스턴스입니다.  
  
 `proName`  
 필수 요소. 문자열 속성 이름의 값입니다.  
  
## <a name="remarks"></a>설명  
 `propertyIsEnumerable` 메서드 반환 `true` 경우 `proName` 에 존재 `object` 를 사용 하 여 열거할 수는 `For` 루프입니다. `propertyIsEnumerable` 메서드 반환 `false` 경우 `object` 지정 된 이름의 속성이 없는 했거나 열거 가능한 지정된 된 속성이 없는 경우. 일반적으로 미리 정의 된 속성은을 열거할 수 있지만 사용자 정의 속성은 항상 열거할 합니다.  
  
 `propertyIsEnumerable` 메서드 프로토타입 체인에 있는 개체를 고려 하지 않습니다.  
  
## <a name="example"></a>예제  
  
```JavaScript  
var a = new Array("apple", "banana", "cactus");  
document.write(a.propertyIsEnumerable(1));  
  
// Output: true  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [prototype 속성(Object)](../../javascript/reference/prototype-property-object-javascript.md)