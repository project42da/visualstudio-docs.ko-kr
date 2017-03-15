---
title: "컴파일러 오류 CS0766 | Microsoft Docs"
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
  - "CS0766"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0766"
ms.assetid: 4574e30b-3e76-42cd-90e8-31c72126a08c
caps.latest.revision: 4
caps.handback.revision: 4
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0766
부분 메서드\(Partial Method\)의 반환 형식은 void여야 합니다.  
  
 부분 메서드\(Partial Method\)는 값을 반환할 수 없습니다. 반환 형식은 void여야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  부분 메서드\(Partial Method\)에 void 반환 형식을 지정하거나 메서드를 일반\(부분이 아님\) 메서드로 변환합니다.  
  
## 예제  
 다음 예제에서는 CS0766을 생성합니다.  
  
```  
// cs0766.cs using System; public partial class C { partial int Part(); // CS0766 // Typically the implementing declaration // is contained in a separate file. partial int Part() //CS0766 { } public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)