---
title: "parseFloat 함수 (JavaScript) | Microsoft Docs"
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
- parseFloat
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- parseFloat method
ms.assetid: a7d87a69-1919-4623-be85-972e6376dd2d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eb8f6d179abba887542e59d083141534732ed42a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="parsefloat-function-javascript"></a>parseFloat 함수(JavaScript)
문자열을 부동 소수점 숫자로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
parseFloat(numString)   
```  
  
## <a name="remarks"></a>설명  
 필요한 `numString` 인수는 부동 소수점 숫자를 포함 하는 문자열입니다.  
  
 `parseFloat` 함수에 포함 된 숫자와 동일한 숫자 값을 반환 `numString`합니다. 하는 경우의 접두사 `numString` 를 부동 소수점 숫자로 구문 분석할 수 `NaN` (숫자가 아님) 반환 됩니다.  
  
```JavaScript  
parseFloat("abc")      // Returns NaN.  
parseFloat("1.2abc")   // Returns 1.2.  
```  
  
 테스트할 수 있습니다 `NaN` 를 사용 하 여 `isNaN` 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [전역 개체](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [isNaN 함수](../../javascript/reference/isnan-function-javascript.md)   
 [parseInt 함수](../../javascript/reference/parseint-function-javascript.md)   
 [String 개체](../../javascript/reference/string-object-javascript.md)