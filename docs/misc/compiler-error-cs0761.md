---
title: "컴파일러 오류 CS0761 | Microsoft Docs"
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
  - "CS0761"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0761"
ms.assetid: b16ac1df-0ddc-44d2-89f1-8d9c32af87ad
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0761
'method\<T\>'의 부분 메서드\(Partial Method\) 선언에 일관성이 없는 형식 매개 변수 제약 조건이 있습니다.  
  
 부분 메서드\(Partial method\)가 구현인 경우 제네릭 형식 제약 조건은 메서드 서명에 정의된 제약 조건과 동일해야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  제네릭 형식 제약 조건을 부분 메서드\(Partial method\)의 각 부분에서 동일하게 만듭니다.  
  
## 예제  
 다음 코드에서는 CS0761을 생성합니다.  
  
```  
// cs0761.cs using System; public partial class C { partial void Part<T>() where T : class; partial void Part<T>() where T : struct // CS0761 { } public static int Main() { return 1; } }  
  
```  
  
## 참고 항목  
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)   
 [형식 매개 변수에 대한 제약 조건](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)