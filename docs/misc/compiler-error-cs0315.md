---
title: "컴파일러 오류 CS0315 | Microsoft Docs"
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
  - "CS0315"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0315"
ms.assetid: 9bb1cab3-1dca-4467-978b-1ab310901a70
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0315
제네릭 형식 또는 메서드 'TypeorMethod\<T\>'에서 'valueType' 형식을 'T' 형식 매개 변수로 사용할 수 없습니다. 'valueType'에서 'referenceType'으로의 boxing 변환이 없습니다.  
  
 이 오류는 제네릭 형식을 특정 클래스로 제한하고 암시적으로 boxing할 수 없는 값 형식을 사용하여 해당 클래스의 인스턴스를 생성하려는 경우에 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  한 가지 해결 방법은 구조체를 클래스로 다시 정의하는 것입니다.  
  
## 예제  
 다음 예제에서는 CS0315를 생성합니다.  
  
```  
// cs0315.cs public class ClassConstraint { } public struct ViolateClassConstraint { } public class Gen<T> where T : ClassConstraint { } public class Test { public static int Main() { Gen<ViolateClassConstraint> g = new Gen<ViolateClassConstraint>(); //CS0315 return 1; } }  
```  
  
## 참고 항목  
 [형식 매개 변수에 대한 제약 조건](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)   
 [boxing 및 unboxing](/dotnet/csharp/programming-guide/types/boxing-and-unboxing)