---
title: "컴파일러 오류 CS0262 | Microsoft Docs"
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
  - "CS0262"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0262"
ms.assetid: 44f8661f-c934-483f-84cd-00ca8257e50a
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0262
'type'의 partial 선언에 충돌하는 접근성 한정자가 포함되어 있습니다.  
  
 이 오류는 부분 형식에 public, private, protected, internal 또는 abstract와 같은 일치하지 않는 한정자가 있는 경우에 발생합니다. 해당 형식에 대한 모든 partial 선언에서 이러한 한정자가 일치해야 합니다. 자세한 내용은 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0262를 생성합니다.  
  
```  
// CS0262.cs class A { public partial class C  // CS0262 { } private partial class C { } }  
```