---
title: "더하기 할당 연산자 (+ =) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: +=
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- addition assignment operator (+=)
- += operator
- assignment operators, JavaScript
ms.assetid: 8517d05c-38b0-4107-bea4-253eb420f438
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 38d86c537dda90dd7f44923b97384b3609dad5ba
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="addition-assignment-operator--javascript"></a>더하기 할당 연산자(+=)(JavaScript)
변수 값에 식 값을 더하고 결과를 변수에 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result += expression   
```  
  
## <a name="parameters"></a>매개 변수  
 `result`  
 모든 변수입니다.  
  
 `expression`  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 이 연산자를 사용 하는 정확히 지정과 같은: `result = result + expression`합니다.  
  
 동작을 결정 하는 두 식의 형식에서 `+=` 연산자입니다.  
  
|조건|결과|  
|--------|----------|  
|두 식이 모두 숫자 또는 부울|추가|  
|두 식이 모두 문자열|연결|  
|한 식이 숫자이 고 다른 하나는 문자열|연결|  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [더하기 연산자 (+)](../../javascript/reference/addition-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)