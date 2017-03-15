---
title: "컴파일러 오류 CS0625 | Microsoft Docs"
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
  - "CS0625"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0625"
ms.assetid: 44091813-9988-436c-b35e-e24094793782
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0625
'field': StructLayout\(LayoutKind.Explicit\)으로 표시된 인스턴스 필드 형식에는 FieldOffset 특성이 있어야 합니다.  
  
 구조체가 명시적 **StructLayout** 특성으로 표시된 경우 구조체의 모든 필드에 [FieldOffset](frlrfsystemruntimeinteropservicesfieldoffsetattributeclasstopic) 특성이 있어야 합니다. 자세한 내용은 [StructLayoutAttribute 클래스](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic)를 참조하세요.  
  
 다음 샘플에서는 CS0625를 생성합니다.  
  
```  
// CS0625.cs // compile with: /target:library using System; using System.Runtime.InteropServices; [StructLayout(LayoutKind.Explicit)] struct A { public int i;   // CS0625 not static; an instance field } // OK [StructLayout(LayoutKind.Explicit)] struct B { [FieldOffset(5)] public int i; }  
```