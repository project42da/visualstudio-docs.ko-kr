---
title: "Date 개체가 필요 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT5006
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d6ab82e6-ca64-46b4-a06c-5c6b0aa057cb
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 05e27b822f933ade811084552f6f0379257ae82e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="date-object-expected"></a>Date 개체가 필요합니다.
호출 하려고는 **Date.prototype.toString** 또는 **Date.prototype.valueOf** 아닌 다른 형식의 개체에서 메서드 `Date`합니다. 이 형식의 호출 개체 유형 이어야 `Date`합니다. 예:  
  
```JavaScript  
var o = new Object;  
o.f = Date.prototype.toString;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   호출할는 **Date.prototype.toString** 또는 **Date.prototype.valueOf** 형식의 개체에 대 한 메서드 `Date`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Date 개체](../../javascript/reference/date-object-javascript.md)   
 [getDate 메서드 (Date)](../../javascript/reference/getdate-method-date-javascript.md)   
 [내장 개체](../../javascript/intrinsic-objects-javascript.md)