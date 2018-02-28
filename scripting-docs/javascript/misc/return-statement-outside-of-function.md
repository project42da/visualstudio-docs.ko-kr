---
title: "&#39; return&#39; 함수 외부 문 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT1018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 03568f9f-5f4f-4a10-a738-9a73f3832b9e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07b633c87dc11b291a5a5783f8121b2a368996d6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="39return39-statement-outside-of-function"></a>&#39; return&#39; 함수 외부 문
사용한는 `return` 코드의 전역 범위에서 문을 합니다. `return` 함수의 본문 안에 문을 사용할만 해야 합니다.  
  
 사용 하는 함수를 호출 하는 `()` 연산자는 식입니다. 모든 식은 같을 값이 있습니다. `return` 문을 사용 하는 함수에 의해 반환 되는 값을 지정 합니다. 일반 형식은 다음과 같습니다.  
  
```  
  
return [ expression ];  
```  
  
 경우는 `return` 문이 실행 될 *식* 평가 되 고 함수의 값으로 반환 합니다. 식이 없는 경우 **정의 되지 않은** 반환 됩니다.  
  
 함수 실행이 중지 될 때는 `return` 문이 실행 되는 함수 본문에 여전히 남아 있는 다른 문의 경우에 합니다. 이 규칙에 대 한 예외 경우는 **반환** 문 내에서 발생 한 **시도** 블록 및 해당 하는 **마지막으로** 블록을 코드는  **마지막으로** 블록 함수가 반환 되기 전에 실행 됩니다.  
  
 실행 하지 않고도 함수 본문의 끝에도 달했기 때문에 함수가 반환 하는 경우는 `return` 문, 반환 값은 고 **정의 되지 않은** 값 (즉, 더 큰 수식의 일부로 함수 결과 사용할 수 없습니다 ).  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   제거는 `return` (전역 범위) 코드의 본문에서 문의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [return 문](../../javascript/reference/return-statement-javascript.md)   
 [함수 개체](../../javascript/reference/function-object-javascript.md)   
 [caller 속성(Function)](../../javascript/reference/caller-property-function-javascript.md)