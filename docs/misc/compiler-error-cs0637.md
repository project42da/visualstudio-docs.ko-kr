---
title: "컴파일러 오류 CS0637 | Microsoft Docs"
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
  - "CS0637"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0637"
ms.assetid: 02f6964c-0fcc-4f81-8ebb-0330aecdde19
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0637
static 또는 const 필드에는 FieldOffset 특성을 사용할 수 없습니다.  
  
 [FieldOffset](frlrfsystemruntimeinteropservicesfieldoffsetattributeclasstopic) 특성은 [정적](/dotnet/csharp/language-reference/keywords/static) 또는 [const](/dotnet/csharp/language-reference/keywords/const)로 표시된 필드에 사용할 수 없습니다.  
  
 다음 샘플에서는 CS0637을 생성합니다.  
  
```  
// CS0637.cs using System; using System.Runtime.InteropServices; [StructLayout(LayoutKind.Explicit)] public class MainClass { [FieldOffset(3)]   // CS0637 public static int i; public static void Main () { } }  
```