---
title: "컴파일러 경고(수준 1) CS0658 | Microsoft Docs"
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
  - "CS0658"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0658"
ms.assetid: 0309074c-741a-492c-9370-73b4bbfd3c1a
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS0658
'attribute modifier'는 인식할 수 있는 특성 위치가 아닙니다. 이 블록의 모든 특성이 무시됩니다.  
  
 특성 한정자를 잘못 지정했습니다. 자세한 내용은 [특성 대상](http://msdn.microsoft.com/ko-kr/59a261f0-1cfb-4aa5-b610-6b735389882c)을 참조하세요.  
  
 다음 샘플에서는 CS0658을 생성합니다.  
  
```  
// CS0658.cs using System; public class TestAttribute : Attribute{} [badAttributeLocation: Test]   // CS0658, badAttributeLocation is invalid class ClassTest { public static void Main() { } }  
```