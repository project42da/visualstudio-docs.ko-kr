---
title: "부호 없는 오른쪽 시프트 연산자 (&gt;&gt;&gt;) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '>>>'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- unsigned right shift operator (>>>)
- '>>> operator'
ms.assetid: df48bdfc-8741-46ab-b681-449da57ac95c
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: efb873bedc0a64089c7ec892d6378b4869c0ca21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="unsigned-right-shift-operator-gtgtgt-javascript"></a>부호 없는 오른쪽 시프트 연산자 (&gt;&gt;&gt;) (JavaScript)
오른쪽으로 부호를 유지 하지는 식의 비트를 이동 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = expression1 >>> expression2  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *expression1*  
 임의의 식입니다.  
  
 *expression2*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 **>>>**  연산자의 비트를 이동 *expression1* 에 지정 된 비트 수 만큼 오른쪽 *expression2*합니다. 0으로 왼쪽에서 입력 됩니다. 오른쪽에서 이동 된 자릿수는 무시 됩니다. 예:  
  
```JavaScript  
var temp  
temp = -14 >>> 2  
```  
  
 변수 *temp* 의 초기 값은-14 (2의 보수 이진수에서 11111111 11111111 11111111 11110010). 만큼된 오른쪽으로 두 비트 이면 값은 1073741820이 됩니다 (이진수 00111111 11111111 11111111 11111100)로 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [부호 없는 오른쪽 시프트 할당 연산자 (>>> =)](../../javascript/reference/unsigned-right-shift-assignment-operator-decrement-equal-javascript.md)   
 [비트 왼쪽 시프트 연산자 (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [비트 오른쪽 시프트 연산자 (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)