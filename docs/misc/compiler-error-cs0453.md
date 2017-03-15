---
title: "컴파일러 오류 CS0453 | Microsoft Docs"
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
  - "CS0453"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0453"
ms.assetid: a1bbd09e-6313-4bfd-84bf-bc15a8d214a6
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0453
제네릭 형식 또는 메서드 'Generic Identifier'에서 'Type Name' 형식을 'Parameter Name' 매개 변수로 사용하려면 해당 형식이 null을 허용하지 않는 값 형식이어야 합니다.  
  
 이 오류는 **value** 제약 조건이 있는 제네릭 형식 또는 메서드를 인스턴스화할 때 값이 아닌 형식 인수를 사용하는 경우에 발생합니다. nullable 값 형식 인수를 사용하는 경우에도 발생할 수 있습니다. 다음 예제에서 마지막 두 줄의 코드를 참조하세요.  
  
## 예제  
 다음 코드에서는 이 오류를 생성합니다.  
  
```  
// CS0453.cs using System; public class HV<S> where S : struct { } public class H1 : HV<string> { }                   // CS0453 public class H2 : HV<H1> { }                       // CS0453 public class H3<S> : HV<S> where S : class { }     // CS0453 public class H4 : HV<int?> { }                     // CS0453 public class H5 : HV<Nullable<Nullable<int>>> { }  // CS0453  
```