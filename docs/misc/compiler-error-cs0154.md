---
title: "컴파일러 오류 CS0154 | Microsoft Docs"
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
  - "CS0154"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0154"
ms.assetid: 815150da-09b4-4593-825f-1dd435c92da8
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0154
'property' 속성 또는 인덱서는 get 접근자가 없으므로 이 컨텍스트에 사용할 수 없습니다.  
  
 get 접근자 메서드가 속성에 정의되어 있지 않으므로 [property](/dotnet/csharp/programming-guide/classes-and-structs/using-properties)를 사용하려는 시도가 실패했습니다. 자세한 내용은 [필드](/dotnet/csharp/programming-guide/classes-and-structs/fields)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0154를 생성합니다.  
  
```  
// CS0154.cs public class MyClass2 { public int i { set { } // uncomment the get method to resolve this error /* get { return 0; } */ } } public class MyClass { public static void Main() { MyClass2 myClass2 = new MyClass2(); int j = myClass2.i;   // CS0154, no get method } }  
```