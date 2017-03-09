---
title: "단일 형식 지정자로 선언된 여러 개의 변수로는 명시적으로 초기화할 수 없습니다. | Microsoft Docs"
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
  - "bc30671"
  - "vbc30671"
helpviewer_keywords: 
  - "BC30671"
ms.assetid: 57bbdd58-b58d-4144-8fa6-366a7167df27
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 단일 형식 지정자로 선언된 여러 개의 변수로는 명시적으로 초기화할 수 없습니다.
같은 줄에서 여러 변수를 선언하는 경우 초기화가 허용되지 않습니다.  
  
 **오류 ID:** BC30671  
  
### 이 오류를 해결하려면  
  
1.  각 항목을 별도로 선언하고 초기화합니다.  
  
2.  여러 항목을 함께 선언한 다음 각 항목을 초기화합니다. 예를 들면 다음과 같습니다.  
  
    ```  
    Dim x, b, i As Integer x = 9 : b = 9 : i = 9 ' ":" is the same as a new line.  
    ```  
  
## 참고 항목  
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [변수 선언](/dotnet/visual-basic/programming-guide/language-features/variables/variable-declaration)