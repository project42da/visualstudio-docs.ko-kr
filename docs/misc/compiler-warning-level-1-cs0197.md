---
title: "컴파일러 경고(수준 1) CS0197 | Microsoft Docs"
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
  - "CS0197"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0197"
ms.assetid: 2b5b1b8d-ce13-4bd7-b80a-abb80e9f79ad
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS0197
'argument'는 참조로 마샬링하는 클래스의 필드이므로 ref 또는 out으로 전달하거나 해당 주소를 가져오면 런타임 예외가 발생할 수 있습니다.  
  
 <xref:System.MarshalByRefObject>에서 직접 또는 간접적으로 파생되는 클래스는 참조로 마샬링하는 클래스입니다. 이러한 클래스는 프로세스 및 컴퓨터 경계에서 참조로 마샬링할 수 있습니다. 따라서 이 클래스의 인스턴스는 원격 개체에 대한 프록시일 수 있습니다. 프록시 개체의 필드를 [ref](/dotnet/csharp/language-reference/keywords/ref) 또는 [out](/dotnet/csharp/language-reference/keywords/out)으로 전달할 수 없습니다. 따라서 인스턴스가 프록시 개체가 될 수 없는 [this](/dotnet/csharp/language-reference/keywords/this)가 아닌 경우 이러한 클래스의 필드를 `ref` 또는 `out`으로 전달할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS0197을 생성합니다.  
  
```  
// CS0197.cs // compile with: /W:1 class X : System.MarshalByRefObject { public int i; } class M { public int i; static void AddSeventeen(ref int i) { i += 17; } static void Main() { X x = new X(); x.i = 12; AddSeventeen(ref x.i);   // CS0197 // OK M m = new M(); m.i = 12; AddSeventeen(ref m.i); } }  
```