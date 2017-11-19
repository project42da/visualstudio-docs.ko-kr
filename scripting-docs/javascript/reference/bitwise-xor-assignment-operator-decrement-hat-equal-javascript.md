---
title: "비트 XOR 대입 연산자 (^ =) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ^=
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ^= operator, about ^= operator
- assignment operators, bitwise [JavaScript]
- bitwise operators, XOR operator
- XOR operator
- ^= operator
ms.assetid: a6ded216-27b6-4fc4-a51b-7d10cc6f820c
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 511ff5b3346bb2b04bf4c24cb3e0b715b2ccf4c5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-xor-assignment-operator--javascript"></a>비트 배타적 OR 할당 연산자(^=)(JavaScript)
변수와 식의 비트 배타적 OR 연산을 수행하고 결과를 변수에 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result ^= expression  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *식*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 사용 하는  **^=**  연산자는 정확 하 게 지정과 동일 합니다.  
  
```JavaScript  
result = result ^ expression  
```  
  
 **^=**  연산자는 두 식의 값의 이진 표현에는 비트 배타적 OR 연산을 수행 합니다. 이 작업의 결과 다음과 같이 동작합니다.  
  
```JavaScript  
0101    (result)  
1100    (expression)  
----  
1001    (result)  
```  
  
 를 한 개만, 식의 값은 1 숫자 때의 결과 값은 1 해당에서 합니다. 그렇지 않은 경우 해당 숫자가 결과 값은 0이 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [비트 배타적 OR 연산자 (^)](../../javascript/reference/bitwise-xor-operator-decrement-hat-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)