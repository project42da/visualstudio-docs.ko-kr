---
title: "Throw 따라야 할 식에서 같은 소스 줄에서 | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT1035
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b03b7747-01a1-40c6-af80-a1dd70bc5781
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7179a22d2713c9ddc894618bd6921f3f873f2ad8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="throw-must-be-followed-by-an-expression-on-the-same-source-line"></a>같은 소스 줄에서 throw 뒤에는 식이 와야 합니다.
사용한는 `throw` 키워드를 따르지 않은 것 하는 식으로 같은 소스 줄에 있지만 합니다. A `throw` 문의 두 부분으로 구성:는 `throw` 키워드와 throw 될 식입니다. 예:  
  
```JavaScript  
if (denominator == 0) {  
 throw new DivideByZeroException();  
}  
```  
  
 이 두 구성 요소 분할할 수 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   다음 사항을 확인는 `throw` 키워드와 throw 식이 같은 줄에 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [Error 개체](../../javascript/reference/error-object-javascript.md)   
 [throw 문](../../javascript/reference/throw-statement-javascript.md)   
 [try...catch...finally 문](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)