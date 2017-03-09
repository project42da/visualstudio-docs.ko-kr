---
title: "컴파일러 경고(수준 1) CS1957 | Microsoft Docs"
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
  - "CS1957"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1957"
ms.assetid: a4823211-52ce-4ffa-b19b-ee874069409f
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1957
'name' 멤버가 'method'를 재정의합니다. 런타임에 여러 재정의 후보가 있습니다. 호출되는 메서드는 구현별로 다릅니다.  
  
 `ref` 또는 `out`인지에 의해서만 달라지는 메서드 매개 변수는 런타임에 구분할 수 없습니다.  
  
### 이 경고를 방지하려면  
  
1.  메서드 중 하나에 다른 이름이나 다른 개수의 매개 변수를 제공합니다.  
  
## 예제  
 다음 코드에서는 CS1957을 생성합니다.  
  
```  
// cs1957.cs class Base<T, S> { public virtual string Test(out T x) // CS1957 { x = default(T); return "Base.Test"; } public virtual void Test(ref S x) { } } class Derived : Base<int, int> { public override string Test(out int x) { x = 0; return "Derived.Test"; } static int Main() { int x; if (new Derived().Test(out x) == "Derived.Test") return 0; return 1; } }  
```