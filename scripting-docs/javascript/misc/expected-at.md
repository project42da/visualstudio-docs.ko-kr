---
title: "&#39;@&#39;가 필요합니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT1032"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 82ff8b74-1710-4358-9a26-dc92ab29c53b
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# &#39;@&#39;가 필요합니다.
`@set` 문을 사용하여 조건부 컴파일 문에 사용할 변수를 만들려고 했지만 변수 이름 앞에 "**@**" 기호를 삽입하지 않았습니다.  
  
### 이 오류를 해결하려면  
  
-   변수 이름 바로 앞에 "**@**" 기호를 추가하세요.  예를 들면 다음과 같습니다.  
  
    ```javascript  
    @set @myvar = 1  
    ```  
  
## 참고 항목  
 [@set 문](../../javascript/reference/at-set-statement-javascript.md)   
 [조건부 컴파일](../../javascript/advanced/conditional-compilation-javascript.md)   
 [조건부 컴파일 변수](../../javascript/advanced/conditional-compilation-variables-javascript.md)