---
title: "컴파일러 경고(수준 3) CS0661 | Microsoft Docs"
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
  - "CS0661"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0661"
ms.assetid: c218665e-5947-40bb-b633-d268483e6522
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 3) CS0661
'class'는 \=\= 연산자 또는 \!\= 연산자를 정의하지만 Object.GetHashCode\(\)를 재정의하지 않습니다.  
  
 컴파일러에서 사용자 정의 같음 또는 같지 않음 연산자는 검색했지만 **GetHashCode** 함수에 대한 재정의는 검색하지 못했습니다. 사용자 정의 같음 또는 같지 않음 연산자는 **GetHashCode** 함수를 재정의하고자 함을 나타냅니다.  
  
 다음 샘플에서는 CS0661을 생성합니다.  
  
```  
// CS0661.cs // compile with: /W:3 class Test   // CS0661 { public static bool operator == (object o, Test t) { return true; } public static bool operator != (object o, Test t) { return true; } public override bool Equals(object o) { return true; } // uncomment the GetHashCode function to resolve // public override int GetHashCode() // { //    return 0; // } public static void Main() { } }  
```