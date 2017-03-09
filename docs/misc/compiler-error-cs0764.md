---
title: "컴파일러 오류 CS0764 | Microsoft Docs"
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
  - "CS0764"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0764"
ms.assetid: 76a64149-49d8-40ea-a976-03835d8fb7eb
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0764
두 부분 메서드\(Partial Method\) 선언 모두 unsafe이거나 unsafe가 아니어야 합니다.  
  
 부분 메서드\(Partial Method\)는 하나의 정의 선언\(서명\)과 선택적 구현 선언\(본문\)으로 구성됩니다. 정의 선언에 `unsafe` 한정자가 있을 경우 구현 선언에도 있어야 합니다. 반대로, 구현 선언에 `unsafe` 한정자가 있을 경우 정의 선언에도 있어야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  정의 선언이 올바른 경우 정의 선언에 맞게 구현 선언에 `unsafe` 한정자를 추가하거나 제거합니다.  
  
## 예제  
  
```  
// cs0764.cs //  Compile with: /target:library /unsafe public partial class C { partial void Part(); unsafe partial void Part() //CS0764 { } public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)