---
title: "컴파일러 오류 CS0264 | Microsoft Docs"
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
  - "CS0264"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0264"
ms.assetid: a8a87185-5915-4b0d-a8cd-2f129ea51b8f
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0264
'type'의 partial 선언에서는 형식 매개 변수 이름과 그 순서가 같아야 합니다.  
  
 이 오류는 partial 선언에서 제네릭 형식을 정의하는 중 전체 partial 선언에서 형식 매개 변수의 이름 또는 순서가 일치하지 않는 경우 발생합니다. 이 오류를 해결하려면 각 partial 선언의 형식 매개 변수를 확인하고 매개 변수의 동일한 이름 및 순서가 사용되는지 확인합니다. 자세한 내용은 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods) 및 [제네릭 형식 매개 변수](/dotnet/csharp/programming-guide/generics/generic-type-parameters)를 참조하세요.  
  
## 예제  
 다음 예제에서는 CS0264를 생성합니다.  
  
```  
// CS0264.cs partial class MyClass<T>  // CS0264 { } partial class MyClass <MyType> { }  
```