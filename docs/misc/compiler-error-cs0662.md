---
title: "컴파일러 오류 CS0662 | Microsoft Docs"
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
  - "CS0662"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0662"
ms.assetid: 836fa15e-3bf3-4af5-8acf-072d7d731dcd
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0662
'method'는 ref 매개 변수에 Out 특성만 지정할 수는 없습니다. In 및 Out 특성을 모두 사용하거나 둘 다 사용하지 마세요.  
  
 인터페이스 메서드에 [ref](/dotnet/csharp/language-reference/keywords/ref)에서 [Out](frlrfSystemRuntimeInteropServicesOutAttributeClassTopic) 특성만 사용하는 매개 변수가 있습니다.**Out** 특성을 사용하는 `ref` 매개 변수는 [In](frlrfSystemRuntimeInteropServicesInAttributeClassTopic) 특성도 사용해야 합니다.  
  
 다음 샘플에서는 CS0662를 생성합니다.  
  
```  
// CS0662.cs using System.Runtime.InteropServices; interface I { void method([Out] ref int i);   // CS0662 // try one of the following lines instead // void method(ref int i); // void method([Out, In]ref int i); } class test { public static void Main() { } }  
```