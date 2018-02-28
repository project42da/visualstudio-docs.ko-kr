---
title: "지원 되지 않는 값 인수에 순환 참조가 | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT5034
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 5d06f0fa-86f5-49d1-8d50-af1759990f43
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d25489065ceece41108a75c9d3763a95e4adb924
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="circular-reference-in-value-argument-not-supported"></a>값 인수에 순환 참조를 사용하는 것은 지원되지 않습니다.
호출 하려고 `JSON.stringify` 유효 하지 않은 값을 사용 합니다. `value` 인수, 배열 또는 개체를 순환 참조를 포함 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   인수에서 순환 참조를 제거 합니다.  
  
## <a name="example"></a>예제  
 이 예제의 코드 때문에 런타임 오류를 발생 `john` 에 대 한 참조가 `mary` 및 `mary` 에 대 한 참조가 `john`합니다. 순환 참조를 제거 하려면 제거 하거나 하거나 설정을 해제 속성 `brother` 에서 `mary` 개체 또는 `sister` 에서 속성의 `john` 개체입니다.  
  
```JavaScript  
var john = new Object();  
var mary = new Object();  
john.sister = mary;  
mary.brother = john;  
  
// This line causes a runtime error.  
var error = JSON.stringify(john);  
```  
  
## <a name="see-also"></a>참고 항목  
 [JSON 개체](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript 런타임 오류](../../javascript/reference/javascript-run-time-errors.md)