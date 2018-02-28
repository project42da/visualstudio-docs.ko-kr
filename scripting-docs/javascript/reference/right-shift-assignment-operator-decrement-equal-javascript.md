---
title: "오른쪽 시프트 할당 연산자 (&gt;&gt;=) (JavaScript) | Microsoft Docs"
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
- '>>='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '>>= operator [JavaScript]'
- right shift operators [JavaScript]
- assignment operators, JavaScript
ms.assetid: 8c1f7f90-e3ac-42ee-94f2-5ccc47d7aef6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cb93d146ad00bd19c09fb4cfca3af776a11f245d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="right-shift-assignment-operator-gtgt-javascript"></a>오른쪽 시프트 할당 연산자 (&gt;&gt;=) (JavaScript)
부호를 유지하고 변수 값을 식 값에 지정된 비트 수만큼 오른쪽으로 이동하고 결과를 변수에 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result >>= expression  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *식*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 사용 하는  **>>=**  연산자는 정확 하 게 지정과 동일 합니다.  
  
```JavaScript  
result = result >> expression  
```  
  
 **>>=**  연산자의 비트를 이동 *결과* 에 지정 된 비트 수 만큼 오른쪽 *식*합니다. 비트의 부호 *결과* 왼쪽에서 숫자를 채우는 데 사용 됩니다. 오른쪽에서 이동 된 자릿수는 무시 됩니다. 예를 들어, 다음 코드를 계산 *temp* 값은-4: 14 (11110010) 오른쪽으로 두 비트 equals-4 (11111100)을 향해 이동 합니다.  
  
```JavaScript  
var temp  
temp = -14  
temp >>= 2  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [비트 왼쪽 시프트 연산자 (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [비트 오른쪽 시프트 연산자 (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [부호 없는 오른쪽 시프트 연산자 (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)