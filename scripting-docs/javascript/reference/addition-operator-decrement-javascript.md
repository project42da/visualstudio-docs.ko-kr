---
title: "더하기 연산자 (+) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: +
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- arithmetic operators, addition
- strings [Visual Studio], concatenating
- concatenation operators, vs. addition operator
- addition operator
- + operator
ms.assetid: ec1237d3-e78b-4e77-bd7d-c0204cf03acd
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 70ff02b1f234da7b88d28e66da82262ccef7bfaf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="addition-operator--javascript"></a>더하기 연산자(+)(JavaScript)
다른 두 숫자 식의 값을 추가 하거나 두 문자열을 연결 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = expression1 + expression2  
```  
  
## <a name="parameters"></a>매개 변수  
 `result`  
 모든 변수입니다.  
  
 `expression1`  
 임의의 식입니다.  
  
 `expression2`  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 동작을 결정 하는 두 식의 형식에서  **+**  연산자입니다.  
  
|조건|결과|  
|--------|----------|  
|두 식이 모두 숫자 또는 부울|추가|  
|두 식이 모두 문자열|연결|  
|한 식이 숫자이 고 다른 하나는 문자열|연결|  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [더하기 할당 연산자 (+ =)](../../javascript/reference/addition-assignment-operator-decrement-equal-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)