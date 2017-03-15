---
title: "컴파일러 오류 CS0550 | Microsoft Docs"
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
  - "CS0550"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0550"
ms.assetid: 57278c17-443c-40f2-9ebd-853558743564
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0550
'accessor’가 'property' 인터페이스 멤버에 없는 접근자를 추가합니다.  
  
 파생 클래스에서 속성의 구현에는 기본 인터페이스에서 지정하지 않은 접근자가 포함됩니다.  
  
 자세한 내용은 [속성 사용](/dotnet/csharp/programming-guide/classes-and-structs/using-properties)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0550을 생성합니다.  
  
```  
// CS0550.cs namespace x { interface ii { int i { get; // add the following accessor to resolve this CS0550 // set; } } public class a : ii { int ii.i { get { return 0; } set {}   // CS0550  no set in interface } public static void Main() {} } }  
```