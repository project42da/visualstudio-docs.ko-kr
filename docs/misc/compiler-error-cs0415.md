---
title: "컴파일러 오류 CS0415 | Microsoft Docs"
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
  - "CS0415"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0415"
ms.assetid: 1ed45b02-4568-4af4-b2a6-c8b01230d19a
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0415
'IndexerName' 특성은 명시적 인터페이스 멤버 선언이 아닌 인덱서에서만 사용할 수 있습니다.  
  
 이 오류는 인덱서에서 인터페이스의 명시적 구현이었던 IndexerName 특성을 사용하는 경우 발생합니다. 이 오류는 인덱서의 선언에서 인터페이스 이름을 제거하면\(가능한 경우\) 방지할 수 있습니다. 자세한 내용은 [IndexerNameAttribute 클래스](frlrfSystemRuntimeCompilerServicesIndexerNameAttributeClassTopic)를 참조하세요.  
  
 다음 샘플에서는 CS0415를 생성합니다.  
  
```  
// CS0415.cs using System; using System.Runtime.CompilerServices; public interface IA { int this[int index] { get; set; } } public class A : IA { [IndexerName("Item")]  // CS0415 int IA.this[int index] // Try this line instead: // public int this[int index] { get { return 0; } set { } } static void Main() { } }  
```