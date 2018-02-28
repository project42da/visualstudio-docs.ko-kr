---
title: "예외가 throw 되었지만 잡히지 | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT5022
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b5235490-a8e7-42e3-804e-d85235bc6f05
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 839ff08da4d26406b508a206c809b0813d2b32e1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="exception-thrown-and-not-caught"></a>예외가 throw되었지만 catch할 수 없습니다.
포함 되어 있습니다는 `throw` 사용자 코드에서 문 내에 포함 하지는 **시도** 블록 또는 더 연결 했습니다 **catch** 오류를 트래핑 하는 블록입니다. 내에서 예외가 throw 됩니다는 **시도** 사용 하 여는 **throw** 문, 및 외부 검색 되었습니다는 **시도** 블록와 함께 한 **catch** 문입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   코드에서 예외를 throw 할 수 있는 한 **시도** 을 차단 하 고 해당 하는 확인 **catch** 블록입니다.  
  
-   Catch 문을에서는 올바른 형식의 예외가 있는지 확인 합니다.  
  
-   예외가 다시 throw 되는 경우 해당 catch 문을 다른 인지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Error 개체](../../javascript/reference/error-object-javascript.md)   
 [throw 문](../../javascript/reference/throw-statement-javascript.md)   
 [try...catch...finally 문](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)