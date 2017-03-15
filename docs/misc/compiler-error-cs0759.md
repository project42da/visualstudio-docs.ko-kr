---
title: "컴파일러 오류 CS0759 | Microsoft Docs"
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
  - "CS0759"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0759"
ms.assetid: 96f0e178-adbf-4327-8934-ac282c428184
caps.latest.revision: 4
caps.handback.revision: 4
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0759
'method' 부분 메서드\(Partial Method\)의 구현 선언에 대한 정의 선언이 없습니다.  
  
 부분 메서드에 메서드의 서명\(이름, 반환 형식 및 매개 변수\)을 정의하는 정의 선언이 있어야 합니다. 구현 또는 메서드 본문은 선택 사항입니다.  
  
### 이 오류를 해결하려면  
  
1.  partial 클래스 또는 구조체의 다른 부분에 부분 메서드에 대한 정의 선언을 제공합니다.  
  
## 예제  
 다음 예제에서는 CS0759를 생성합니다.  
  
```  
// cs0759.cs using System; public partial class C { partial void Part() // CS0759 { } public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)