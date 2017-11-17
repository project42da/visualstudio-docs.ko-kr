---
title: "Math.max 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: max
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: max method
ms.assetid: f3ea1b8a-5fd0-482a-971b-b7f8e2b9b7eb
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: adf66164346f3802d92f8e0de82356df49bad5fa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="mathmax-function-javascript"></a>Math.max 함수(JavaScript)
제공 된 숫자 식의 집합 중 더 큰 숫자를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Math.max([number1[, number2[... [, numberN]]]])   
```  
  
## <a name="remarks"></a>설명  
 선택적 `number1, number2, ..., numberN` 인수는 숫자 식이 계산 됩니다.  
  
 반환 값이 같지 없는 인수를 제공 하는 경우 [Number.NEGATIVE_INFINITY](../../javascript/reference/number-constants-javascript.md)합니다. 인수가 있으면 `NaN`, 반환 값은 또한 `NaN`합니다.  
  
## <a name="example"></a>예제  
 다음 코드에는 두 식 중 더 큰 숫자를 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var x = Math.max(107 - 3,  48 * 90);  
document.write(x);  
  
// Output:  
// 4320  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Math.min 함수](../../javascript/reference/math-min-function-javascript.md)