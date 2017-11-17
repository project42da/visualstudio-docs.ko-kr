---
title: "논리 연산자 (| |) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '||'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '|| operator'
- logical OR operator
ms.assetid: 95295331-6269-4311-8391-dc1c68e116ab
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 80c8e1bcae57e13642a0c77ae75c7c2aac58ace6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="logical-or-operator--javascript"></a>논리합 연산자(||)(JavaScript)
두 식의 논리합 연산을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = expression1 || expression2  
```  
  
## <a name="parameters"></a>매개 변수  
 *결과*  
 모든 변수입니다.  
  
 *expression1*  
 임의의 식입니다.  
  
 *expression2*  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 식 중 하나 또는 둘 다로 계산 되 면 **True**, *결과* 은 **True**합니다. 다음 표에서 설명 방법을 *결과* 결정 됩니다.  
  
|경우 `expression1` 은|및 `expression2` 은|`result` 은|  
|-------------------------|--------------------------|---------------------|  
|True|True|True|  
|True|False|True|  
|False|True|True|  
|False|False|False|  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서는 부울이 아닌 값을 부울 값으로 변환하는 데 다음과 같은 규칙을 사용합니다.  
  
-   개체를 모두 true으로 간주 됩니다.  
  
-   문자열은 비어 있는 경우에 false 간주 합니다.  
  
-   `null`정의 되지 않은 및 false 것으로 간주 됩니다.  
  
-   숫자는 경우에만 이면 false, 0.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)