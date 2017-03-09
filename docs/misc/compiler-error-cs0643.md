---
title: "컴파일러 오류 CS0643 | Microsoft Docs"
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
  - "CS0643"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0643"
ms.assetid: beae30ff-15c2-413f-8f5c-504cdba2e57a
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0643
'arg'는 중복 명명된 특성 인수입니다.  
  
 사용자 정의 특성에서 `arg` 매개 변수가 두 번 지정되었습니다. 자세한 내용은 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0643을 생성합니다.  
  
```  
// CS0643.cs using System; using System.Runtime.InteropServices; [AttributeUsage(AttributeTargets.Class)] public class MyAttribute : Attribute { public MyAttribute() { } public int x; } [MyAttribute(x = 5, x = 6)]   // CS0643, error setting x twice // try the following line instead // [MyAttribute(x = 5)] class MyClass { } public class MainClass { public static void Main () { } }  
```