---
title: "비트 OR 할당 연산자 (| =) (JavaScript) | Microsoft Docs"
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
- '|='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- assignment operators, bitwise [JavaScript]
- '|= operator'
- bitwise operators, OR operator
- OR operator
ms.assetid: 9b424ff6-4442-4621-b3b6-83e7fd1e5cd5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8ce9cadcf07906c9eba6749706620ae6293c2682
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-or-assignment-operator--javascript"></a>비트 논리합 할당 연산자(|=)(JavaScript)
변수 값과 식 값의 비트 OR 연산을 수행하고 결과를 변수에 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result |= expression  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *식*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 이 연산자를 사용 하 여 같습니다 정확 하 게 지정:  
  
```JavaScript  
result = result | expression  
```  
  
 **&#124; =** 연산자의 값의 이진 표현 살펴봅니다 *결과* 및 *식* 에 대해 비트 OR 연산을 수행 합니다. 이 작업의 결과 다음과 같이 동작합니다.  
  
```JavaScript  
0101    (result)  
1100    (expression)  
----  
1101    (output)  
```  
  
 자릿수 중 하나가 식의 값은 1이 숫자 이면 결과 해당에서 값은 1입니다. 그렇지 않은 경우 해당 숫자가 결과 값은 0이 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [비트 OR 연산자 (&#124;)](../../javascript/reference/bitwise-or-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)