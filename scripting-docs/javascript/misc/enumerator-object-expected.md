---
title: "Enumerator 개체가 필요 합니다 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT5015
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: dc6e32c1-a6e6-4e12-ac99-e3f65f91c8d7
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 485e6e387f07fd3a54727f5f8e08c0a00743c6d9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="enumerator-object-expected"></a>Enumerator 개체가 필요합니다.
호출 하려고는 **Enumerator.prototype.atEnd, Enumerator.prototype.item, Enumerator.prototype.moveFirst,** 또는 **Enumerator.prototype.moveNext** 형식의 다른 개체에서 메서드 보다 `Enumerator`합니다. 이 형식의 호출 개체 유형 이어야 `Enumerator`합니다. 이 규칙을 중단 하는 코드 예제는 다음과 같습니다.  
  
```JavaScript  
var o = new Object;  
o.f = Enumerator.prototype.atEnd;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   호출할는 **Enumerator.prototype.atEnd**, **Enumerator.prototype.item**, **Enumerator.prototype.moveFirst**, 또는  **Enumerator.prototype.moveNext** 형식의 개체에 대 한 메서드 `Enumerator`합니다. 개체를 했는지 확인 하는 프로그램 `Enumerator` 개체를 가져오려면:  
  
    ```  
    if(x instanceof Enumerator)  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [Enumerator 개체](../../javascript/reference/enumerator-object-javascript.md)