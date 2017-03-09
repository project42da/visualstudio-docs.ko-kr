---
title: "컴파일러 오류 CS0669 | Microsoft Docs"
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
  - "CS0669"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0669"
ms.assetid: c7f81869-79d7-481f-a026-2cef0e87df4c
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0669
ComImport 특성이 있는 클래스에는 사용자 정의 생성자를 사용할 수 없습니다.  
  
 공용 언어 런타임의 COM interop 계층에서 [ComImport](frlrfSystemRuntimeInteropServicesComImportAttributeClassTopic) 클래스에 대한 생성자를 제공합니다. 따라서 COM 개체를 런타임에 관리 개체로 사용할 수 있습니다.  
  
 다음 샘플에서는 CS0669를 생성합니다.  
  
```  
// CS0669.cs using System.Runtime.InteropServices; [ComImport, Guid("00000000-0000-0000-0000-000000000001")] class TestClass { TestClass()   // CS0669, delete constructor to resolve { } public static void Main() { } }  
```