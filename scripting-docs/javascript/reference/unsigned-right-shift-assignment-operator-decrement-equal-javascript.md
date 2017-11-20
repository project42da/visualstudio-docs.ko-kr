---
title: "부호 없는 오른쪽 시프트 할당 연산자 (&gt;&gt;&gt;=) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '>>>='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '>>>= operator'
- unsigned right shift assignment operator (>>>=)
- assignment operators, JavaScript
ms.assetid: f67c3737-7d39-41ae-9c11-8b16d38f6179
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1272cbb58645df605743c6790642cd0e295442aa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="unsigned-right-shift-assignment-operator-gtgtgt-javascript"></a>부호 없는 오른쪽 시프트 할당 연산자 (&gt;&gt;&gt;=) (JavaScript)
부호를 유지하지 않고 변수 값을 식 값에 지정된 비트 수만큼 오른쪽으로 이동하고 결과를 변수에 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result >>>= expression  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *식*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여는 >>> = 연산자는 정확 하 게 다음과 같은 방법으로 동일 합니다.  
  
```JavaScript  
result = result >>> expression  
```  
  
 **>>>=**  연산자의 비트를 이동 *결과* 에 지정 된 비트 수 만큼 오른쪽 *식*합니다. 0으로 왼쪽에서 입력 됩니다. 오른쪽에서 이동 된 자릿수는 무시 됩니다. 예:  
  
```JavaScript  
var temp  
temp = -14  
temp >>>= 2  
```  
  
 변수 *temp* 의 초기 값은-14 (2의 보수 이진수에서 11111111 11111111 11111111 11110010). 두 비트 오른쪽 이동 된 경우 값은 1073741820이 됩니다 (이진수 00111111 11111111 11111111 11111100)로 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [부호 없는 오른쪽 시프트 연산자 (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [비트 왼쪽 시프트 연산자 (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [비트 오른쪽 시프트 연산자 (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)