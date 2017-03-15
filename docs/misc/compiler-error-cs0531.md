---
title: "컴파일러 오류 CS0531 | Microsoft Docs"
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
  - "CS0531"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0531"
ms.assetid: 54c2a98b-84e3-481a-a934-7cd6dffa7677
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0531
'member': 인터페이스 멤버에는 정의를 사용할 수 없습니다.  
  
 [인터페이스](/dotnet/csharp/language-reference/keywords/interface)에서 선언된 메서드는 인터페이스 자체가 아니라 이 인터페이스에서 상속된 클래스에서 구현되어야 합니다.  
  
 다음 샘플에서는 CS0531을 생성합니다.  
  
```  
// CS0531.cs namespace x { public interface clx { int xclx()   // CS0531, cannot define xclx // Try the following declaration instead: // int xclx(); { return 0; } } public class cly { public static void Main() { } } }  
```