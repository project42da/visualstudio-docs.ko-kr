---
title: "컴파일러 오류 CS0411 | Microsoft Docs"
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
  - "CS0411"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0411"
ms.assetid: 290947c9-10d0-427e-99f2-bff20299d533
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0411
'method' 메서드의 형식 인수를 유추할 수 없습니다. 형식 인수를 명시적으로 지정하세요.  
  
 이 오류는 형식 인수를 명시적으로 제공하지 않고 제네릭 메서드를 호출하고 컴파일러에서 원하는 형식 인수를 유추할 수 없는 경우 발생합니다. 이 오류를 방지하려면 꺾쇠 괄호에 원하는 형식 인수를 추가합니다.  
  
## 예제  
 다음 샘플에서는 CS0411을 생성합니다.  
  
```  
// CS0411.cs class C { void G<T>() { } public static void Main() { G();  // CS0411 // Try this instead: // G<int>(); } }  
```  
  
## 예제  
 기타 가능한 오류 사례에는 매개 변수가 `null`, 즉 형식 정보가 없는 경우가 포함됩니다.  
  
```  
// CS0411b.cs class C { public void F<T>(T t) where T : C { } public static void Main() { C c = new C(); c.F(null);  // CS0411 } }  
```