---
title: "컴파일러 경고(수준 2) CS0279 | Microsoft Docs"
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
  - "CS0279"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0279"
ms.assetid: 5e5faa8f-3d5b-4999-aa62-ff7f131a3e04
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0279
'type name'이 'pattern name' 패턴을 구현하지 않습니다. 'method name’이 static이거나 아니면 public이 아닙니다.  
  
 C\#에는 `foreach` 및 `using`과 같이 정의된 패턴을 사용하는 문이 여러 개 있습니다. 예를 들어 `foreach`는 열거 가능 패턴을 구현하는 컬렉션 클래스를 사용합니다. 이 오류는 `public`이 아닌 `static`으로 선언된 메서드로 인해 컴파일러가 일치시킬 수 없을 때 발생합니다. 패턴의 메서드는 클래스의 인스턴스여야 하고 public이어야 합니다.  
  
## 예제  
 다음 예제에서는 CS0279를 생성합니다.  
  
```  
// CS0279.cs using System; using System.Collections; public class myTest : IEnumerable { IEnumerator IEnumerable.GetEnumerator() { yield return 0; } internal IEnumerator GetEnumerator() { yield return 0; } public static void Main() { foreach (int i in new myTest()) {}  // CS0279 } }  
```