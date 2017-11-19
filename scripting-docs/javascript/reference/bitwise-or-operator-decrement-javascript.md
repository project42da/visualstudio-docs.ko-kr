---
title: "비트 연산자 (| |) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '|'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- bitwise operators, OR operator
- OR operator
- '| operator'
ms.assetid: ffc8f758-3151-478e-bafb-fc78f1c469a0
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a91c616c84b9d38154bf936f61fb856a4ebad0f7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-or-operator--javascript"></a>비트 논리합 연산자(|)(JavaScript)
두 식의 비트 OR 연산을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = expression1 | expression2  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *expression1*  
 임의의 식입니다.  
  
 *expression2*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 **&#124;** 연산자는 두 식의 값의 이진 표현에는 비트 OR 연산을 수행 합니다. 이 작업의 결과 다음과 같이 동작합니다.  
  
```JavaScript  
0101   (expression1)  
1100   (expression2)  
----  
1101   (result)  
```  
  
 자릿수 중 하나가 식의 값은 1이 숫자 이면 결과 1이 해당에서 합니다. 그렇지 않으면 결과 해당 숫자가에 0을 갖습니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [비트 OR 할당 연산자 (&#124; =)](../../javascript/reference/bitwise-or-assignment-operator-decrement-equal-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)