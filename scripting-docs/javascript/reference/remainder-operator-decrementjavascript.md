---
title: "나머지 연산자 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '%'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- remainder operator, JavaScript
- '% operator [JavaScript]'
- Remainder function [JavaScript]
ms.assetid: 087d654f-623b-498d-95ff-596d26bf674d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce74b8512b25cfe215d294873102b274623b42a2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="remainder-operator-javascript"></a>나머지 연산자 (JavaScript)
각 식의 값을 다른 값으로 나누고 나머지를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = number1 % number2  
```  
  
## <a name="arguments"></a>인수  
 `result`  
 모든 변수입니다.  
  
 `number1`  
 임의의 숫자 식입니다.  
  
 `number2`  
 임의의 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 나머지 연산자 나눕니다 `number1` 여 `number2`으로 나머지만 반환 `result`합니다. 부호 `result` 의 부호와 같습니다 `number1`합니다. 값 `result` 0에서의 절대 값 사이의 `number2`합니다.  
  
 다음 코드에는 나머지 연산자를 사용 하는 방법을 보여 줍니다.  
  
```  
var modResult = 19 % 6.7;  
document.write(modResult);  
  
// Output: 5.6  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)
