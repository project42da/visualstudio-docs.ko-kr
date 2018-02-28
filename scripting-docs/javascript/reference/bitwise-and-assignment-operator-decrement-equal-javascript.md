---
title: "비트 논리곱 할당 연산자 (&amp;=) (JavaScript) | Microsoft Docs"
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
- '&='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '&= operator'
- assignment operators, bitwise [JavaScript]
- AND operator
- bitwise operators, AND operator
ms.assetid: e7e2eabb-4fc1-4fdc-9dd8-1e6d715371fa
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dfd2a77e66296cafc6c8403570f0536e1333e081
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-and-assignment-operator-amp-javascript"></a>비트 논리곱 할당 연산자 (&amp;=) (JavaScript)
변수 값에 비트 AND 연산의 결과 식의 값을 설정 합니다. 변수 및 식 32 비트 정수로 처리 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result &= expression  
```  
  
## <a name="parameters"></a>매개 변수  
 `result`  
 모든 변수입니다.  
  
 `expression`  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 이 연산자를 사용 하 여 지정과 같습니다.  
  
```JavaScript  
result = result & expression  
```  
  
 [비트 AND 연산자 (&)](../../javascript/reference/bitwise-and-operator-decrement-javascript.md) 값의 이진 표현에 `result` 및 `expression` 에 비트 AND 연산을 수행 합니다. 이 작업의 출력은 다음과 같이 동작합니다.  
  
```JavaScript  
// 9 is 00000000000000000000000000001001  
var expr1 = 9;  
  
// 5 is 00000000000000000000000000000101  
var expr2 = 5;  
  
// 1 is 00000000000000000000000000000001  
expr1 &= expr2;  
  
document.write(expr1);  
```  
  
 숫자에는 두 식이 모두는 1이 든 지는 결과 값은 1 해당에서 합니다. 그렇지 않은 경우 해당 숫자가 결과 값은 0이 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [비트 논리곱 연산자 (&)](../../javascript/reference/bitwise-and-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)