---
title: "빼기 연산자 (-) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '-'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '- operator, about - operator'
- '- operator'
- negation operator
- subtraction operator, syntax
- arithmetic operators, subtraction
- operators, subtraction
ms.assetid: cd0681d3-15cd-49fe-b4dd-e087de55d778
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb79aab0a57c733871dbfc73ac96c7ddbf4db37c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="subtraction-operator---javascript"></a>빼기 연산자(-)(JavaScript)
단일 식으로 단항 부정 연산자를 제공 하거나 다른 한 식의 값을 뺍니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = number1 - number2;  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 숫자 변수입니다.  
  
 `number`  
 임의의 숫자 식입니다.  
  
 `number1`  
 임의의 숫자 식입니다.  
  
 `number2`  
 임의의 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 구문 1에서의  **-**  연산자는 산술 빼기 연산자는 두 숫자 간의 차이 확인 하는 데 사용 합니다. 구문 2의 경우에  **-**  연산자는 단항 부정 연산자는 식의 음수 값을 나타내는 데 사용 합니다.  
  
 구문 2는 다른 모든 단항 연산자와 마찬가지로 다음과 같이 계산 됩니다.  
  
-   정의 되지 않은에 적용 하는 경우 또는 `null` 식에서 런타임 오류가 발생 합니다.  
  
-   개체를 문자열로 변환 됩니다.  
  
-   가능한 경우 문자열 숫자로 변환 됩니다. 그렇지 않으면 런타임에 오류가 발생 합니다.  
  
-   부울 값은 숫자 (0 false, 1 true)으로 처리 됩니다.  
  
 연산자는 결과 수에 적용 됩니다. 결과 값이 0이 아닌 경우 구문 2에서 *결과* 는 부호를 반대로 바꾼 결과 수와 같습니다. 결과 값이 0 인 경우 *결과* 은 0입니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [빼기 할당 연산자 (-)](../../javascript/reference/subtraction-assignment-operator-decrement-equal-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)