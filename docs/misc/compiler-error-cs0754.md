---
title: "컴파일러 오류 CS0754 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0754"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0754"
ms.assetid: c83e04b5-6ab5-45c2-805e-0ba4f041d506
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0754
부분 메서드\(Partial Method\)는 인터페이스 메서드를 명시적으로 구현할 수 없습니다.  
  
 부분 메서드를 인터페이스에 정의된 메서드의 명시적 구현으로 선언할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  메서드 선언에서 명시적 인터페이스 한정을 제거합니다.  
  
## 예제  
 다음 코드에서는 CS0754를 생성합니다.  
  
```  
// cs0754.cs using System; public interface IF { void Part(); } public partial class C : IF { partial void IF.Part(); //CS0754 public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [명시적 인터페이스 구현](/dotnet/csharp/programming-guide/interfaces/explicit-interface-implementation)   
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)