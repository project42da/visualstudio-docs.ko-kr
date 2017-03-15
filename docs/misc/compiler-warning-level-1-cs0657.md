---
title: "컴파일러 경고(수준 1) CS0657 | Microsoft Docs"
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
  - "CS0657"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0657"
ms.assetid: d12d2efc-f44e-40e6-b825-5a66ead0c08e
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS0657
'attribute modifier'는 이 선언에 유효한 특성 위치가 아닙니다. 이 선언에 유효한 특성 위치는 'locations'입니다. 이 블록의 모든 특성이 무시됩니다.  
  
 컴파일러가 잘못된 위치에서 특성 한정자를 발견했습니다. 자세한 내용은 [특성 대상](http://msdn.microsoft.com/ko-kr/59a261f0-1cfb-4aa5-b610-6b735389882c)을 참조하세요.  
  
 다음 샘플에서는 CS0657을 생성합니다.  
  
```  
// CS0657.cs // compile with: /target:library public class TestAttribute : System.Attribute {} [return: Test]   // CS0657 return not valid on a class class Class1 {}  
```