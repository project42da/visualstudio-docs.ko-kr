---
title: "컴파일러 오류 CS0514 | Microsoft Docs"
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
  - "CS0514"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0514"
ms.assetid: 74ce3010-f9e9-458c-8b68-cfb908a3e7a2
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0514
'constructor': 정적 생성자에는 명시적 'this' 또는 'base' 생성자 호출을 사용할 수 없습니다.  
  
 정적 생성자는 클래스 인스턴스를 만들기 전에 자동으로 호출되기 때문에 정적 생성자에서 `this`를 호출할 수 없습니다. 또한 정적 생성자는 상속되지 않고 직접 호출할 수 없습니다.  
  
 자세한 내용은 [this](/dotnet/csharp/language-reference/keywords/this) 및 [base](/dotnet/csharp/language-reference/keywords/base)를 참조하세요.  
  
## 예제  
 다음 예제에서는 CS0514를 생성합니다.  
  
```  
// CS0514.cs class A { static A() : base(0) // CS0514 { } public A(object o) { } } class B { static B() : this(null) // CS0514 { } public B(object o) { } }  
```