---
title: "parseInt 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: parseInt
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: parseInt method
ms.assetid: e86471af-2a0e-4359-83af-f1ac81e51421
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 54ee77470d32410ae46a628d54fc3bda97fecc51
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="parseint-function-javascript"></a>parseInt 함수(JavaScript)
문자열을 정수로 변환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
parseInt(numString, [radix])   
```  
  
## <a name="parameters"></a>매개 변수  
 `numString`  
 필수 요소. 여러 변환 하는 문자열입니다.  
  
 `radix`  
 선택 사항입니다. 값 2와 지정 된 숫자의 기수로 36 사이의 `numString`합니다. 이 인수가 제공 되지 않은 경우에 '0x' 접두사가 포함 된 문자열 16 진수 간주 됩니다. 다른 모든 문자열 decimal 간주 됩니다.  
  
## <a name="remarks"></a>설명  
 `parseInt` 함수는 정수 값에 포함 된 숫자와 동일한 반환 `numString`합니다. 하는 경우의 접두사 `numString` 를 정수로 구문 분석할 수 `NaN` (숫자가 아님) 반환 됩니다.  
  
```JavaScript  
parseInt("abc");     // Returns NaN.  
parseInt("12abc");   // Returns 12.  
```  
  
 테스트할 수 있습니다 `NaN` 를 사용 하 여 `isNaN` 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [전역 개체](../../javascript/reference/global-object-javascript.md)  
  
> [!NOTE]
>  부터는 [!INCLUDE[jsv9textspecific](../../javascript/reference/includes/jsv9textspecific-md.md)], `parseInt` 함수 진수로 '0' 접두사가 포함 된 문자열을 처리 하지 않습니다. 그러나 사용 하지 않는 경우는 `parseInt` 함수, '0' 접두사가 포함 된 문자열을 octals로 해석 여전히 수 합니다. 참조 [데이터 형식](../../javascript/data-types-javascript.md) 8 진수 정수에 대 한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [isNaN 함수](../../javascript/reference/isnan-function-javascript.md)   
 [parseFloat 함수](../../javascript/reference/parsefloat-function-javascript.md)   
 [String 개체](../../javascript/reference/string-object-javascript.md)   
 [valueOf 메서드(Object)](../../javascript/reference/valueof-method-object-javascript.md)