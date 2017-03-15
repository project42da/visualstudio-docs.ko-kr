---
title: "조건부 컴파일 식에는 Nullable 형식을 사용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc33111"
  - "vbc33111"
helpviewer_keywords: 
  - "BC33111"
ms.assetid: 2c2587e5-2179-4a31-bcf7-7004db6f2d73
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 조건부 컴파일 식에는 Nullable 형식을 사용할 수 없습니다.
nullable 형식은 조건부 컴파일 지시문의 식에 사용할 수 없습니다. 예를 들어 다음 코드에서는 이 오류를 생성합니다.  
  
```vb#  
'#Const triggerPoint = 0 '' Not valid. '#If CType(triggerpoint, Boolean?) = True Then '        ' Body of the conditional directive. '#End If  
```  
  
 **오류 ID:** BC33111  
  
### 이 오류를 해결하려면  
  
-   Nullable 형식 지정을 제거합니다.  
  
## 참고 항목  
 [Nullable Value Types](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)   
 [\#If...Then...\#Else Directives](/dotnet/visual-basic/language-reference/directives/if-then-else-directives)   
 [Conditional Compilation](/dotnet/visual-basic/programming-guide/program-structure/conditional-compilation)