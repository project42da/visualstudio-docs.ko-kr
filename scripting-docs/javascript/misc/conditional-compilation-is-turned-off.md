---
title: "조건부 컴파일이 해제되었습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.WebClient.Help.SCRIPT1030"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 59a030b0-a6c6-47f2-b90e-c0ed204d5116
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 조건부 컴파일이 해제되었습니다.
먼저 조건부 컴파일을 설정하지 않은 상태로 조건부 컴파일 변수를 사용하려고 했습니다.  조건부 컴파일을 설정하면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 컴파일러가 @로 시작하는 식별자를 조건부 컴파일 변수로 해석할 수 있습니다.  이렇게 하려면 다음과 같이 문에서 조건부 코드를 시작합니다.  
  
```  
/*@cc_on @*/  
```  
  
### 이 오류를 해결하려면  
  
-   다음 문을 조건부 코드의 시작 부분에 추가합니다.  
  
    ```javascript  
    /*@cc_on @*/  
    ```  
  
## 참고 항목  
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)   
 [조건부 컴파일 변수](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc\_on 문](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@if 문](../../javascript/reference/at-if-statement-javascript.md)   
 [@set 문](../../javascript/reference/at-set-statement-javascript.md)