---
title: "컴파일러 오류 CS0179 | Microsoft Docs"
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
  - "CS0179"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0179"
ms.assetid: bef000ca-64d7-4809-b2a0-de6927b04b0d
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0179
'member'는 extern일 수 없으며 본문을 선언합니다.  
  
 클래스 멤버가 [extern](/dotnet/csharp/language-reference/keywords/extern)으로 표시되는 경우 해당 멤버의 정의가 다른 파일에 있다는 것입니다. 따라서 **extern**으로 표시된 클래스 멤버는 클래스에서 정의할 수 없습니다.`extern` 키워드를 제거하거나 정의를 삭제합니다. 자세한 내용은 [메서드](/dotnet/csharp/programming-guide/classes-and-structs/methods)을 참조하세요.  
  
 다음 샘플에서는 CS0179를 생성합니다.  
  
```  
// CS0179.cs public class MyClass { public extern int ExternMethod(int aa)   // CS0179 { return 0; } // try the following line instead // public extern int ExternMethod(int aa); public static void Main() { } }  
```