---
title: "&#39;Throw&#39; 피연산자는 &#39;System.Exception&#39;에서 파생되어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30665"
  - "bc30665"
helpviewer_keywords: 
  - "BC30665"
ms.assetid: 7c228087-39ea-4b30-a410-6ba711e67e5e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Throw&#39; 피연산자는 &#39;System.Exception&#39;에서 파생되어야 합니다.
`Throw`에 제공된 인수는 `System.Exception` 인스턴스 또는 `System.Exception`에서 파생된 클래스의 인스턴스여야 합니다.  
  
 **오류 ID:** BC30665  
  
### 이 오류를 해결하려면  
  
-   다음 예제와 같이 `System.Exception`에서 파생된 인수를 사용합니다.  
  
    ```  
    Throw New System.Exception("This is an error.")  
    ```  
  
## 참고 항목  
 [Throw Statement](/dotnet/visual-basic/language-reference/statements/throw-statement)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic의 예외 클래스](http://msdn.microsoft.com/ko-kr/9aac396f-34ca-4afb-8e6c-e523cb690ba9)   
 [Visual Basic에서 예외 및 오류 처리](http://msdn.microsoft.com/ko-kr/3e351e73-cf23-40ab-8b60-05794160529e)