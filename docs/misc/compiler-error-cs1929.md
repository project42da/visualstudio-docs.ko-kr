---
title: "컴파일러 오류 CS1929 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1929"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1929"
ms.assetid: effdd5d4-e156-418b-9d45-4ca194ab4319
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1929
인스턴스 인수: 'typeA'에서 'typeB'로 변환할 수 없습니다.  
  
 이 오류는 확장하지 않는 클래스에서 확장 메서드를 호출하려고 할 때 발생합니다. 여기에 표시된 예제에서 확장 메서드가 파생 클래스 `A`에 대해 정의되었지만 기본 클래스 `B`에 대해서는 정의되지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  호출해야 하는 곳에서 형식에 대한 새 확장 메서드를 만들거나 호출을 기존 메서드가 확장하는 형식의 개체로 이동합니다.  
  
## 예제  
 다음 코드에서는 CS1928 및 CS1929을 생성합니다.  
  
```  
// cs1929.cs using System.Linq; using System.Collections; static class Ext { public static void ExtMethod(this A a) { } } class A : B { } class B { static void Main() { B b = new B(); b.ExtMethod(); // CS1929 } }  
```  
  
## 참고 항목  
 [확장 메서드](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)