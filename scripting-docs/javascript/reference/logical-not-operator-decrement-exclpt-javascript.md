---
title: "논리 부정 연산자 (!) (JavaScript) | Microsoft Docs"
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
- '!'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Logical NOT operator
- '! operator'
- '! operator, about ! operator'
ms.assetid: 68c3dc71-ae95-4293-9155-67405846d71d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29c27b9cd670989eb2112de5067e68bd09d76903
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="logical-not-operator--javascript"></a>논리 부정 연산자(!)(JavaScript)
식의 논리 부정 연산을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = !expression  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *식*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 다음 표에서 설명 방법을 *결과* 결정 됩니다.  
  
|경우 `expression` 은|그런 다음 `result` 은|  
|------------------------|----------------------|  
|True|False|  
|False|True|  
  
 모든 단항 연산자와 같은 **!** 다음과 같이 식을 계산 합니다.  
  
-   정의 되지 않은에 적용 하는 경우 또는 `null` 식에서 런타임 오류가 발생 합니다.  
  
-   개체를 문자열로 변환 됩니다.  
  
-   가능한 경우 문자열 숫자로 변환 됩니다. 그렇지 않으면 런타임에 오류가 발생 합니다.  
  
-   부울 값은 숫자 (0 false, 1 true)으로 처리 됩니다.  
  
 연산자는 결과 수에 적용 됩니다.  
  
 에 대 한는 **!** 연산자를 경우 *식* 이 값은 0 *결과* 은 0입니다. 경우 *식* 0 이면 *결과* 는 1입니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [비트 NOT 연산자 (~)](../../javascript/reference/bitwise-not-operator-decrement-tilde-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)