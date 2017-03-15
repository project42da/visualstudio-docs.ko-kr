---
title: "컴파일러 오류 CS1950 | Microsoft Docs"
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
  - "CS1950"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1950"
ms.assetid: e37fb5b1-09e0-47a6-9db5-a48f90ea7bbb
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1950
오버로드된 Add 메서드 중 해당 컬렉션 이니셜라이저에 가장 적합한 'name'에 일부 잘못된 인수가 있습니다.  
  
 컬렉션 이니셜라이저를 지원하려면 클래스에 IEnumerable이 구현되고 공용 `Add` 메서드가 있어야 합니다. 컬렉션 이니셜라이저를 사용하여 형식을 초기화하려면 `Add` 메서드의 입력 매개 변수가 추가하려는 개체의 형식과 호환되어야 합니다.  
  
### 이 오류를 해결하려면  
  
-   컬렉션 이니셜라이저에서 호환되는 형식을 사용합니다.  
  
-   입력 매개 변수 및\/또는 컬렉션 형식의 `Add` 메서드 접근성을 수정합니다.  
  
-   전달하고 있는 대상과 일치하는 입력 매개 변수를 사용하여 새 `Add` 메서드를 추가합니다.  
  
-   전달하는 형식을 허용하는 `Add` 메서드를 가질 수 있도록 컬렉션 클래스 제네릭을 만듭니다.  
  
## 예제  
 다음 예제에서는 CS1950을 생성합니다.  
  
```  
// cs1950.cs using System.Collections; class TestClass : CollectionBase { public void Add(int c) { } } class Test { static void Main() { TestClass t = new TestClass { "hi" }; // CS1950 } }  
```  
  
## 참고 항목  
 [개체 및 컬렉션 이니셜라이저](/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers)