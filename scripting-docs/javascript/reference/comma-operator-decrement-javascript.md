---
title: "쉼표 연산자 (,) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '%2C'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: comma operator
ms.assetid: 699fa0bf-cd0a-45ee-a291-2fbed4ecd470
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2cb504beefc5ce4c260ec8296e2cf097e17d349e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="comma-operator--javascript"></a>쉼표 연산자(,)(JavaScript)
두 식을 순차적으로 실행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
expression1, expression2  
```  
  
## <a name="parameters"></a>매개 변수  
 `expression1`  
 임의의 식입니다.  
  
 `expression2`  
 임의의 식입니다.  
  
## <a name="remarks"></a>설명  
 `,` 연산자는 왼쪽에서 오른쪽 순서로 실행 될 수 있는 식을 합니다. 일반적인 용도 `,` 의 증가 식에 연산자가는 `for` 루프입니다. 예:  
  
```JavaScript  
j=25;  
for (i = 0; i < 10; i++, j++)  
{  
   k = i + j;  
}  
```  
  
 `for` 문은 모든 루프의 끝에 실행 하도록 단일 식만 허용 합니다. `,` 연산자를 사용 하면 여러 개의 식을 모두 지는 변수를 증가 될 수 있으므로 단일 식으로 처리 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)