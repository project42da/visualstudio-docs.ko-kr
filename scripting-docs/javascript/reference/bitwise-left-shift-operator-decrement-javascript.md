---
title: "비트 왼쪽 시프트 연산자 (&lt;&lt;) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: <<
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- << operator
- left shift operators
- << operator, about << operator
- bitwise operators, Left Shift operator
ms.assetid: 18148596-7b86-4add-aeef-106991c69435
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9d63fc50659695f518e581edbed67c009b36577f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-left-shift-operator-ltlt-javascript"></a>비트 왼쪽 시프트 연산자 (&lt;&lt;) (JavaScript)
왼쪽 식의 비트를 이동합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = expression1 << expression2  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *expression1*  
 임의의 식입니다.  
  
 *expression2*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 **<<**  연산자의 비트를 이동 *expression1* 에 지정 된 비트 수 만큼 왼쪽으로 *expression2*합니다. 예:  
  
```JavaScript  
var temp  
temp = 14 << 2  
```  
  
 변수 *temp* 되므로 14 (이진 00001110) 왼쪽된으로 두 비트 (이진 00111000) 56 56 값이 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [왼쪽 시프트 할당 연산자 (<\<=)](../../javascript/reference/left-shift-assignment-operator-decrement-equal-javascript.md)   
 [비트 오른쪽 시프트 연산자 (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [부호 없는 오른쪽 시프트 연산자 (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)