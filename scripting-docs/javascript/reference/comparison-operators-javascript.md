---
title: "비교 연산자 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Comparison
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- comparison operators, script
- greater than operator
- comparison operators
- greater than or equal to operator
- inequity operator
- identity operator
ms.assetid: 084f90f0-d010-47cf-96dd-13d637fc9b68
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 067d570523fc2241b4f2e0442785a49aedb15200
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="comparison-operators-javascript"></a>비교 연산자(JavaScript)
비교 결과를 나타내는 부울 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
expression1 comparisonoperator expression2  
```  
  
## <a name="parameters"></a>매개 변수  
 `expression1`  
 임의의 식입니다.  
  
 `comparisonoperator`  
 모든 비교 연산자입니다.  
  
 `expression2`  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 문자열을 비교할 때 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 문자열 식의 유니코드 문자 값을 사용 합니다.  
  
 다음 설명 된 형식 및 값에 따라 연산자의 서로 다른 그룹의 동작 방식을 `expression1` 및 `expression2`:  
  
 관계형 연산자: `<`, `>`, `<=`,`>=`  
  
-   둘 다를 변환 하려고 `expression1` 및 `expression2` 숫자로 합니다.  
  
-   두 식이 모두 문자열, 문자열 비교를 수행 합니다.  
  
-   식 중 하나가 `NaN`, return `false`합니다.  
  
-   음수 0은 양의 0을 같습니다.  
  
-   음의 무한대를 사용 하면 자체를 포함 한 모든 보다 작습니다.  
  
-   양의 무한대 자체를 포함 한 모든 보다 큽니다.  
  
 같음 연산자: `==`,`!=`  
  
-   두 식의 형식이 서로 다르면, 문자열, 숫자 또는 부울 값으로 변환 하기 위해 시도 합니다.  
  
-   `NaN`자신을 포함 한 모든 것과 같지 않습니다.  
  
-   음수 0은 양의 0을 같습니다.  
  
-   `null`둘 다 같음 `null` 및 `undefined`합니다.  
  
-   값은 동일한 문자열, 숫자, 동일한 개체, 부울 값 같은 것으로 간주 됩니다 또는 (하는 경우 다른 종류) 이러한 상황 중 하나로 강제 변환할 수 있습니다.  
  
-   다른 모든 비교는 같지 않은 것으로 간주 됩니다.  
  
 Identity 연산자: `===`,`!==`  
  
 이러한 연산자 함수와 똑같이 동작 하지만 같음 연산자를 제외 하 고 형식 변환이 수행 됩니다. 경우 두 식의 형식이 동일 하지, 이러한 식은 항상 반환 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)