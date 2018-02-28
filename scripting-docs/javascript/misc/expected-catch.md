---
title: "예상 &#39; catch &#39; | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT1033
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f1cd947f-eba2-411e-8e84-8ca86f608643
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e6cd1e57137d220ebcf3834070e36d8257e2dca7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="expected-39catch39"></a>예상 &#39; catch &#39;
예외 처리 사용 **시도** 차단 되지만 연결 된 작성 하지 않은 **catch** 문. 예외 처리 메커니즘 내에 있어야는 예외가 발생할 경우를 실행 해야 하는 코드와 함께 실패할 수 있는 코드는 **시도** 블록입니다. 내에서 예외가 throw 됩니다는 **시도** 사용 하 여는 **throw** 문, 및 외부 검색 되었습니다는 **시도** 블록 하나 이상과 **catch**문입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   연결 된 추가 **catch** 블록입니다.  
  
-   사용 하 여 시도 **마지막** 대신 차단는 **catch** 블록입니다.  
  
## <a name="see-also"></a>참고 항목  
 [try … catch 마지막 문...](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)   
 [Error 개체](../../javascript/reference/error-object-javascript.md)