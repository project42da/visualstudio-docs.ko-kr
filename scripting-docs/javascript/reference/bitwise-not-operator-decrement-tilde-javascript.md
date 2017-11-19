---
title: "비트 NOT 연산자 (~) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ~
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- NOT operator
- bitwise operators, NOT operator
ms.assetid: 39f92474-fe05-4a8b-9ad8-caca93f82bca
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aec64b055b260efb7a4b0d952aed9b3a5d7ddc82
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-not-operator--javascript"></a>Bitwise NOT 연산자(~)(JavaScript)
식의 비트 NOT(부정) 연산을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = ~ expression  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *식*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 모든 단항 연산자와 같은 `~` 연산자를 다음과 같이 식을 계산 합니다.  
  
-   정의 되지 않은에 적용 하는 경우 또는 `null` 식에서 런타임 오류가 발생 합니다.  
  
-   개체를 문자열로 변환 됩니다.  
  
-   가능한 경우 문자열 숫자로 변환 됩니다. 그렇지 않으면 런타임에 오류가 발생 합니다.  
  
-   부울 값은 숫자 (0 false, 1 true)으로 처리 됩니다.  
  
 연산자는 결과 수에 적용 됩니다.  
  
 `~` 연산자 식 값의 이진 표현 합니다에 비트 부정 연산을 수행 합니다.  
  
 식에서 1 인 모든 숫자는 결과에 0이 됩니다. 식에서 0 인 모든 숫자는 결과에 1이 됩니다.  
  
 다음 예제에서는 비트의 사용을 보여 줍니다. NOT (~) 연산자.  
  
```  
var temp = ~5;  
```  
  
 결과 값은 다음 표에 나와 있는 것 처럼-6, 합니다.  
  
|식|이진 값 (2의 보수)|10 진수 값|  
|----------------|---------------------------------------|-------------------|  
|5|00000000 00000000 00000000 00000101|5|  
|~5|11111111 11111111 11111111 11111010|-6|  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [논리 부정 연산자 (!)](../../javascript/reference/logical-not-operator-decrement-exclpt-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)