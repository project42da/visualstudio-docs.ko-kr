---
title: "컴파일러 오류 CS0762 | Microsoft Docs"
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
  - "CS0762"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0762"
ms.assetid: 7cedd1af-ffe6-4ca7-82fb-faa9e98014a4
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0762
'method'는 구현 선언이 없는 부분 메서드\(Partial Method\)이므로 이 메서드로부터 대리자를 만들 수 없습니다.  
  
 부분 메서드\(Partial Method\)에는 구현 선언이 없어도 됩니다. 그러나 대리자의 캡슐화된 메서드에는 구현이 있어야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  대리자를 초기화하는 데 사용되는 메서드에 대한 구현을 제공합니다.  
  
## 예제  
  
```  
public delegate void TestDel(); public partial class C { partial void Part(); public static int Main() { C c = new C(); TestDel td = new TestDel(c.Part); // CS0762 return 1; } }  
```