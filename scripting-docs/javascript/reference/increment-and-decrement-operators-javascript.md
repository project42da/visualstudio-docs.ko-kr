---
title: "증가 (+ +) 및 감소 (-) 연산자 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- --
- ++
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- increment operators, syntax
- ++ operator
- ++ operator, about ++ operator
- decrement operators, syntax
- -- operator
ms.assetid: 49eaf4cf-8818-478d-a429-cdd2ece20811
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 806bd321bb1f81d585a6595b8cf2842571164921
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="increment--and-decrement----operators-javascript"></a>증가(++) 및 감소(--) 연산자(JavaScript)
증가 연산자 증가 하 고 감소 연산자 감소 씩 변수의 값입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      result = ++variable  
result = --variable  
result = variable++  
result = variable--  
```  
  
## <a name="parameters"></a>매개 변수  
 `result`  
 모든 변수입니다.  
  
 `variable`  
 모든 변수입니다.  
  
## <a name="remarks"></a>설명  
 연산자가 변수 앞에, 전에 식이 계산 되는 값이 수정 됩니다. 연산자 변수 뒤에 표시를 하는 경우 값은 식이 계산 된 후 수정 됩니다.  즉, 지정 된 `j = ++k;`의 값 `j` 의 원래 값은 `k` 백업과; 한 번 부여 `j = k++;`의 값 `j` 의 원래 값이 `k`, 해당 값이 할당 다음 증가 `j`.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)