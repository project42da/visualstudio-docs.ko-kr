---
title: "열거형 형식은 nullable일 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32129"
  - "bc32129"
helpviewer_keywords: 
  - "BC32129"
ms.assetid: 9e0fe5c9-72c7-4905-b177-d00cc3469ea9
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 열거형 형식은 nullable일 수 없습니다.
열거형을 선언하는 데 사용되는 기본 형식은 nullable일 수 없습니다. 예를 들어 다음 코드는 이 오류를 생성합니다.  
  
```vb#  
'' Not valid. ' Enum exampleEnum As Integer? '     Member declarations. ' End Enum  
```  
  
 **오류 ID:** BC32129  
  
### 이 오류를 해결하려면  
  
-   `Enum` 선언에 nullable 기본 형식을 사용하지 마세요.  
  
## 참고 항목  
 [Nullable Value Types](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)   
 [Enum Statement](/dotnet/visual-basic/language-reference/statements/enum-statement)