---
title: "비트 배타적 OR 연산자 (^) (JavaScript) | Microsoft Docs"
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
- ^
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- bitwise operators, XOR operator
- XOR operator
ms.assetid: 44ef0d18-abb5-4d83-9e77-6394635b3f48
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ebe8ff9805793bf306688622b0b29007b1562e2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-xor-operator--javascript"></a>비트 배타적 OR 연산자(^)(JavaScript)
두 식의 비트 배타적 OR 연산을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = expression1 ^ expression2  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *expression1*  
 임의의 식입니다.  
  
 *expression2*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 **^**  연산자는 두 식의 값의 이진 표현에는 비트 배타적 OR 연산을 수행 합니다. 이 작업의 결과 다음과 같이 동작합니다.  
  
```JavaScript  
0101   (expression1)  
1100   (expression2)  
----  
1001   (result)  
```  
  
 를 한 개만, 식의 값은 1 숫자 때의 결과 값은 1 해당에서 합니다. 그렇지 않은 경우 해당 숫자가 결과 값은 0이 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [비트 XOR 대입 연산자 (^ =)](../../javascript/reference/bitwise-xor-assignment-operator-decrement-hat-equal-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)