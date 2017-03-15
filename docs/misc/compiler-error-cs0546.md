---
title: "컴파일러 오류 CS0546 | Microsoft Docs"
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
  - "CS0546"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0546"
ms.assetid: d259c86f-ee29-4e2d-b381-6ba7252af87e
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0546
'accessor': 'property'에 재정의 가능한 set 접근자가 없으므로 재정의할 수 없습니다.  
  
 접근자를 재정의할 수 없으므로 속성에 대한 접근자 메서드 중 하나를 재정의하지 못했습니다. 이 오류는 다음과 같은 경우에 발생할 수 있습니다.  
  
-   기본 클래스 속성이 [가상](/dotnet/csharp/language-reference/keywords/virtual)으로 선언되지 않았습니다.  
  
-   기본 클래스 속성이 재정의하려는 [get](/dotnet/csharp/language-reference/keywords/get) 또는 [set](/dotnet/csharp/language-reference/keywords/set) 접근자를 선언하지 않습니다.  
  
 기본 클래스 속성을 재정의하지 않으려는 경우 파생 클래스에서 속성 앞에 [new](/dotnet/csharp/language-reference/keywords/new) 키워드를 사용할 수 있습니다.  
  
 자세한 내용은 [속성 사용](/dotnet/csharp/programming-guide/classes-and-structs/using-properties)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 기본 클래스가 속성에 대한 set 접근자를 선언하지 않으므로 CS0546을 생성합니다.  
  
```  
// CS0546.cs // compile with: /target:library public class a { public virtual int i { get { return 0; } } public virtual int i2 { get { return 0; } set {} } } public class b : a { public override int i { set {}   // CS0546 error no set } public override int i2 { set {}   // OK } }  
```  
  
## 참고 항목  
 [속성](/dotnet/csharp/programming-guide/classes-and-structs/properties)