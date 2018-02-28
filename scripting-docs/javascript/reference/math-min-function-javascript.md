---
title: "Math.min 함수 (JavaScript) | Microsoft Docs"
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
- min
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- min method
ms.assetid: a1d7dd85-27ef-45cd-aa2a-f8e80f0b2898
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bb496cff65db11cf6c99d6a6e687f39e20ea857c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="mathmin-function-javascript"></a>Math.min 함수(JavaScript)
숫자 식의 집합 중 더 작은 숫자를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Math.min([number1[, number2[... [,numberN]]]])  
```  
  
## <a name="remarks"></a>설명  
 선택적 `number1, number2, ..., numberN` 인수는 숫자 식이 계산 됩니다.  
  
 반환 값이 같지 없는 인수를 제공 하는 경우 [Number.POSITIVE_INFINITY](../../javascript/reference/number-constants-javascript.md)합니다. 인수가 있으면 `NaN`, 반환 값은 또한 `NaN`합니다.  
  
## <a name="example"></a>예제  
 다음 코드에는 두 식 중 더 작은 숫자를 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var x = Math.min(107 - 3, 48 * 90);  
document.write(x);  
  
// Output:  
// 104  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Math.max 함수](../../javascript/reference/math-max-function-javascript.md)