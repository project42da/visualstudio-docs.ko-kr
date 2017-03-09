---
title: "컴파일러 오류 CS0753 | Microsoft Docs"
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
  - "CS0753"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0753"
ms.assetid: 287dd9da-da74-4290-9fa1-21ef1a8150fe
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0753
메서드, 클래스, 구조체 또는 인터페이스만 partial일 수 있습니다.  
  
 [partial](/dotnet/csharp/language-reference/keywords/partial-type) 한정자는 클래스, 구조체, 인터페이스 및 메서드에만 사용할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  변수 또는 언어 구문에서 `partial` 한정자를 제거합니다.  
  
## 예제  
 다음 코드에서는 CS0753을 생성합니다.  
  
```  
// cs0753.cs using System; public partial class C { partial int num; // CS0753 public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)