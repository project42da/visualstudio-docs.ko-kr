---
title: "비트 논리곱 연산자 (&amp;) (JavaScript) | Microsoft Docs"
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
- '&'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- assignment operators, bitwise [JavaScript]
- '& operator, about & operator'
- AND operator
- '& operator'
- bitwise operators, AND operator
- '& operator, bitwise operators'
ms.assetid: a8c17a55-2599-4518-98d7-671699f4d5f3
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa8b3eec0cbd7c172d08b16120fb54f3be3c6a48
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-and-operator-amp-javascript"></a>비트 논리곱 연산자 (&amp;) (JavaScript)
두 32 비트 식에 비트 AND 연산을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = expression1 & expression2  
```  
  
## <a name="parameters"></a>매개 변수  
 `result`  
 작업의 결과입니다.  
  
 `expression1`  
 임의의 식입니다.  
  
 `expression2`  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 `&` 두 32 비트 식의 비트의 각 비트 AND 연산을 않습니다. 비트의 둘 다 모두 1 이면 결과 1입니다. 그렇지 않으면 반환 됩니다.  
  
|B i t 1|Bit2|And 처리 된 값|  
|----------|----------|-----------------|  
|0|0|0|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
  
 다음 예제를 사용 하는 방법을 보여 줍니다는 `&` 연산자입니다.  
  
```JavaScript  
// 9 is 00000000000000000000000000001001  
var expr1 = 9;  
  
// 5 is 00000000000000000000000000000101  
var expr2 = 5;  
  
// 1 is 00000000000000000000000000000001  
var result = expr1 & expr2;  
  
document.write(result);  
// Output: 1  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [비트 논리곱 할당 연산자 (& =)](../../javascript/reference/bitwise-and-assignment-operator-decrement-equal-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)