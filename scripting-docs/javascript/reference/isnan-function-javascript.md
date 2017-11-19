---
title: "isNaN 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: isNaN
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: isNaN method
ms.assetid: 5af4eb29-72f6-484f-93bd-04ae1261f849
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b7e6d3687e795ea5d5e38308a8af0d73ba7f5ff
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="isnan-function-javascript"></a>isNaN 함수(JavaScript)
값이 예약된 값 `NaN`(숫자 아님)인지 여부를 나타내는 부울 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
isNaN(numValue)   
```  
  
## <a name="return-value"></a>반환 값  
 `Number` 형식으로 변환된 값이 `NaN`이면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## <a name="remarks"></a>설명  
 필요한 `numValue` 내용과 비교할 값이 `NaN`합니다.  
  
 일반적으로 이 메서드를 사용하여 `parseInt` 및 `parseFloat` 메서드의 반환 값을 테스트합니다.  
  
 포함 된 변수 또는 `NaN` 또는 다른 값 자체를 비교할 수도 있습니다. 이 비교 결과 값이 서로 같지 않으면 `NaN`합니다. 때문에 이것이 `NaN` 은 자신에 게와 같지 않은 유일한 값입니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [전역 개체](../../javascript/reference/global-object-javascript.md)  
  
## <a name="example"></a>예제  
  
```JavaScript  
// Returns false.  
isNaN(100);  
  
// Returns false.  
isNaN("100");  
  
// Returns true.  
isNaN("ABC");  
  
// Returns true.  
isNaN("10C");  
  
// Returns true.  
isNaN("abc123");  
  
// Returns true.  
isNaN(Math.sqrt(-1));           
```  
  
## <a name="see-also"></a>참고 항목  
 [isFinite 함수](../../javascript/reference/isfinite-function-javascript.md)   
 [NaN 상수](../../javascript/reference/nan-constant-javascript.md)   
 [parseFloat 함수](../../javascript/reference/parsefloat-function-javascript.md)   
 [parseInt 함수](../../javascript/reference/parseint-function-javascript.md)