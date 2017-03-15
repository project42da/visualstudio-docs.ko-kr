---
title: "컴파일러 오류 CS0763 | Microsoft Docs"
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
  - "CS0763"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0763"
ms.assetid: 940870ba-1250-4365-acaa-7f968ee96c5b
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0763
두 부분 메서드\(Partial Method\) 선언 모두 static이거나 static이 아니어야 합니다.  
  
 부분 메서드\(Partial Method\) 선언에서 한 부분은 정적이고 다른 부분은 비정적일 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  양쪽 부분을 모두 정적 또는 비정적으로 만듭니다.  
  
## 예제  
 다음 코드에서는 CS0763을 생성합니다.  
  
```  
// cs0763.cs using System; public partial class C { static partial void Part(); partial void Part() // CS0763 { } public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)   
 [static](/dotnet/csharp/language-reference/keywords/static)