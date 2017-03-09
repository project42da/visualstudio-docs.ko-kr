---
title: "컴파일러 경고(수준 1) CS0672 | Microsoft Docs"
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
  - "CS0672"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0672"
ms.assetid: 140a8708-97d0-444b-980b-62e74328cafb
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS0672
'member1' 멤버가 사용되지 않는 'member2' 멤버를 재정의합니다. 'member1'에 사용되지 않음 특성을 추가합니다.  
  
 컴파일러가 `obsolete`로 표시된 메서드로의 `override`를 발견했습니다. 그러나 재정의 메서드 자체는 사용되지 않음으로 표시되지 않았습니다. 재정의 메서드를 호출하면 [CS0612](../misc/compiler-warning-level-1-cs0612.md)가 생성됩니다.  
  
 메서드 선언을 검토하고 메서드\(및 모든 재정의\)가 `obsolete`로 표시되어야 하는지 여부를 명시적으로 나타냅니다.  
  
 다음 샘플에서는 CS0672를 생성합니다.  
  
```  
// CS0672.cs // compile with: /W:1 class MyClass { [System.Obsolete] public virtual void ObsoleteMethod() { } } class MyClass2 : MyClass { public override void ObsoleteMethod()   // CS0672 { } } class MainClass { static public void Main() { } }  
```