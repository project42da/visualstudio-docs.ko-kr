---
title: "비트 오른쪽 시프트 연산자 (&gt;&gt;) (JavaScript) | Microsoft Docs"
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
- '>>'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '>> operator'
- '>> operator, about >> operator'
- '>> operator, bitsets'
- bitwise operators, right shift operator
ms.assetid: 89dc57e0-0b0d-49a4-a8ed-56d8bb20f3e3
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 70db0c176b475886a26cfe4c06f7f2f0c9d4fc2a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-right-shift-operator-gtgt-javascript"></a>비트 오른쪽 시프트 연산자 (&gt;&gt;) (JavaScript)
오른쪽 부호를 유지 하는 식의 비트를 이동 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = expression1 >> expression2  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *expression1*  
 임의의 식입니다.  
  
 *expression2*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 >> 연산자의 비트를 이동 *expression1* 에 지정 된 비트 수 만큼 오른쪽 *expression2*합니다. 비트의 부호 *expression1* 왼쪽에서 숫자를 채우는 데 사용 됩니다. 오른쪽에서 이동 된 자릿수는 무시 됩니다. 예를 들어, 다음 코드를 계산 *temp* -4 값:-14 (11110010 2의 보수 이진) 오른쪽으로 두 비트 equals-4 (11111100 2의 보수 이진)을 향해 이동 합니다.  
  
```JavaScript  
var temp  
temp = -14 >> 2  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [비트 왼쪽 시프트 연산자 (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [오른쪽 시프트 할당 연산자 (>> =)](../../javascript/reference/right-shift-assignment-operator-decrement-equal-javascript.md)   
 [부호 없는 오른쪽 시프트 연산자 (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)