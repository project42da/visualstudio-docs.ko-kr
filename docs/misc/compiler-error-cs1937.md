---
title: "컴파일러 오류 CS1937 | Microsoft Docs"
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
  - "CS1937"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1937"
ms.assetid: f13e8dc9-8c20-477e-8b74-7192848e08a2
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1937
'name' 이름이 'equals'의 왼쪽에서 범위 내에 없습니다. 'equals'의 양쪽 식을 서로 바꿔야 합니다.  
  
 `equals` 키워드는 두 식이 같은지 확인하는 `join` 절에서 사용하는 특수 연산자입니다. 왼쪽 소스 시퀀스에 대한 범위 변수는 등호 왼쪽에 있어야 하며 오른쪽 소스에 대한 범위 변수는 등호의 왼쪽에만 있어야 합니다. 이는 다음 코드 예제에서 IntelliSense로 실험하여 확인할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  다음 예제에서 주석으로 처리한 줄에 표시된 것처럼 두 범위 변수의 위치를 바꿉니다.  
  
## 예제  
 다음 예제에서는 CS1937을 생성합니다.  
  
```  
// cs1937.cs using System.Linq; class Test { static void Main() { int[] sourceA = { 1, 2, 3, 4, 5 }; int[] sourceB = { 3, 4, 5, 6, 7 }; var query = from a in sourceA join b in sourceB on b equals a // CS1937 // Try the following line instead. //join b in sourceB on a equals b select new { a, b }; } }  
```  
  
 왼쪽을 일반적으로 "외부" 측면이라고 하고 오른쪽을 일반적으로 "내부" 측면이라고 합니다.  
  
## 참고 항목  
 [join 절](/dotnet/csharp/language-reference/keywords/join-clause)