---
title: "메서드 인수는 괄호로 묶어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30800"
  - "bc30800"
helpviewer_keywords: 
  - "BC30800"
ms.assetid: ecdec760-8b51-474f-acad-17cf8059d83b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 메서드 인수는 괄호로 묶어야 합니다.
프로시저 호출을 제어하는 규칙은 최신 버전의 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 더 간단합니다. 모든 인수는 괄호로 묶어야 합니다.  
  
 **오류 ID:** BC30800  
  
### 이 오류를 해결하려면  
  
-   인수 목록을 괄호로 묶습니다. 예:  
  
    ```  
    MySub(ArrayIndex, NewValue)  
    ```  
  
## 참고 항목  
 [Procedure Calling Sequence Changes in Visual Basic](http://msdn.microsoft.com/ko-kr/4ef1eea6-36cb-4b97-a31b-9ba65e46a9fd)   
 [Procedure Parameters and Arguments](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments)