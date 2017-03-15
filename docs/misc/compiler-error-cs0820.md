---
title: "컴파일러 오류 CS0820 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0820"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0820"
ms.assetid: 38c05162-ef20-42a8-9611-02698360dec5
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0820
암시적 형식 지역 변수에는 배열 이니셜라이저를 할당할 수 없습니다.  
  
 암시적으로 형식화된 배열은 요소 형식이 컴파일러에서 유추되는 배열입니다. 예제 코드와 같이 `new`\[\] 한정자를 사용하여 초기화해야 합니다.  
  
### 이 오류를 해결하려면  
  
-   배열 이니셜라이저와 함께 `new`\[\] 한정자를 사용합니다.  
  
-   암시적 형식 지역 변수를 사용하지 마세요.  
  
## 예제  
 다음 코드에서는 CS0820을 생성하며 암시적으로 형식화된 배열을 올바르게 초기화하는 방법을 보여 줍니다.  
  
```  
//cs0820.cs class G { public static int Main() { var a = { 1,2,3}; //CS0820 // Try using one of the following lines instead. // var b = new[] { 1, 2, 3 }; //int[] b = {1, 2, 3}; return -1; } }  
```  
  
## 참고 항목  
 [암시적으로 형식화한 지역 변수](/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables)