---
title: "조건부 컴파일이 해제 | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT1030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 59a030b0-a6c6-47f2-b90e-c0ed204d5116
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8f2eabb900e24072c8f390061b5d6081de9bc889
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="conditional-compilation-is-turned-off"></a>조건부 컴파일이 해제되었습니다.
에 처음 켜는 조건부 컴파일 없이 조건부 컴파일 변수를 사용 하려고 합니다. 조건부 컴파일을 설정 하면 지시는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] @ 조건부 컴파일 변수로 시작 하는 식별자를 해석 하는 컴파일러입니다. 문 사용 하 여 조건부 코드를 시작 하 여이 작업을 수행 합니다.  
  
```  
/*@cc_on @*/  
```  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   조건부 코드의 시작 부분에 다음 문을 추가 합니다.  
  
    ```JavaScript  
    /*@cc_on @*/  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)   
 [조건부 컴파일 변수](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc_on문](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@if문](../../javascript/reference/at-if-statement-javascript.md)   
 [@set 문](../../javascript/reference/at-set-statement-javascript.md)