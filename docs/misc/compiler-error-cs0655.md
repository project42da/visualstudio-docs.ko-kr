---
title: "컴파일러 오류 CS0655 | Microsoft Docs"
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
  - "CS0655"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0655"
ms.assetid: 8ce340e2-eeeb-476a-8609-ab4bbaf10c44
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0655
'parameter'는 올바른 특성 매개 변수 형식이 아니므로 올바로 명명된 특성 인수가 아닙니다.  
  
 특성에 유효한 매개 변수 형식에 대한 자세한 내용은 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0655를 생성합니다.  
  
```  
// CS0655.cs using System; class MyAttribute : Attribute { // decimal is not valid attribute parameter type public decimal d = 0; public int e = 0; } [My(d = 0)]   // CS0655 // Try the following line instead: // [My(e = 0)] class C { public static void Main() { } }  
```