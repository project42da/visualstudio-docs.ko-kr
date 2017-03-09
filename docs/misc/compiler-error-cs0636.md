---
title: "컴파일러 오류 CS0636 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0636"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0636"
ms.assetid: 47597f89-fbe6-4708-9493-3c86c6f0ce56
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0636
FieldOffset 특성은 StructLayout\(LayoutKind.Explicit\)으로 표시된 형식의 멤버에만 배치할 수 있습니다.  
  
 **FieldOffset** 특성으로 표시된 멤버를 포함하는 경우 구조체 선언의 **StructLayout\(LayoutKind.Explicit\)** 특성을 사용해야 합니다. 자세한 내용은 [FieldOffset](frlrfsystemruntimeinteropservicesfieldoffsetattributeclasstopic)을 참조하세요.  
  
 다음 샘플에서는 CS0636을 생성합니다.  
  
```  
// CS0636.cs using System; using System.Runtime.InteropServices; // To resolve the error, uncomment the following line: // [StructLayout(LayoutKind.Explicit)] struct Worksheet { [FieldOffset(4)]public int i;   // CS0636 } public class MainClass { public static void Main () { } }  
```