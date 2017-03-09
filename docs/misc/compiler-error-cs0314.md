---
title: "컴파일러 오류 CS0314 | Microsoft Docs"
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
  - "CS0314"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0314"
ms.assetid: 12f68f51-0568-4e80-b0fd-15899807477d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0314
제네릭 형식 또는 메서드 'name'에서 'type1' 형식을 형식 매개 변수 'name'으로 사용할 수 없습니다. 'type1'에서 'type2'로의 형식 매개 변수 변환 또는 boxing 변환이 없습니다.  
  
 제네릭 형식이 제한된 형식 매개 변수를 사용하는 경우 새 클래스에서는 동일한 제약 조건을 충족해야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  아래 예제에서 `B` 클래스에 `where T : ClassConstraint`를 추가합니다.  
  
## 예제  
 다음 코드에서는 CS0314를 생성합니다.  
  
```  
// cs0314.cs // Compile with: /target:library public class ClassConstraint { } public class A<T> where T : ClassConstraint { } public class B<T> : A<T> //CS0314 { } // Try using this instead. public class C<T> : A<T> where T : ClassConstraint { }  
```  
  
## 참고 항목  
 [형식 매개 변수에 대한 제약 조건](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)