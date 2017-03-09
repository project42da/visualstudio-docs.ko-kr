---
title: "컴파일러 오류 CS0265 | Microsoft Docs"
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
  - "CS0265"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0265"
ms.assetid: d43d19c2-8a66-4bb1-95a0-557b0a29bce1
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0265
'type'의 partial 선언에는 'type parameter' 형식 매개 변수의 제약 조건에 일관성이 없습니다.  
  
 이 오류는 제네릭 클래스를 partial 클래스로 정의할 때, 해당 partial 정의가 둘 이상의 위치에서 발생하고 제네릭 형식에 대한 제약 조건이 둘 이상의 위치에서 일관적이지 않거나 서로 다른 경우 발생합니다. 둘 이상의 위치에서 제약 조건을 지정하는 경우 모두 동일해야 합니다. 가장 쉬운 방법은 한 곳에서 제약 조건을 지정하고 다른 곳에서는 생략하는 것입니다. 자세한 내용은 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods) 및 [형식 매개 변수에 대한 제약 조건](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)를 참조하세요.  
  
 다음 코드에서는 CS0265 오류를 생성합니다.  
  
## 예제  
 이 코드에서는 partial 클래스 정의가 모두 단일 파일에 있지만 여러 파일에 전파될 수 있습니다.  
  
```  
// CS0265.cs public class GenericsErrors { interface IFace1 { } interface IFace2 { } partial class PartialBadBounds<T> where T : IFace1 { } // CS0265 partial class PartialBadBounds<T> where T : IFace2 { } }  
```