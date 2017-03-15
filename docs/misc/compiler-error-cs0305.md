---
title: "컴파일러 오류 CS0305 | Microsoft Docs"
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
  - "CS0305"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0305"
ms.assetid: a862c484-01fe-4067-b0f4-15a618e7f8a1
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0305
제네릭 형식 'generic type'을 사용하려면 'number' 형식 인수가 필요합니다.  
  
 이 오류는 예상 개수의 형식 인수를 찾을 수 없는 경우 발생합니다. C0305를 해결하려면 필요한 수의 형식 인수를 사용합니다.  
  
## 예제  
 다음 샘플에서는 CS0305를 생성합니다.  
  
```  
// CS0305.cs public class MyList<T> {} public class MyClass<T> {} class MyClass { public static void Main() { MyList<MyClass, MyClass> list1 = new MyList<MyClass>();   // CS0305 MyList<MyClass> list2 = new MyList<MyClass>();   // OK } }  
```