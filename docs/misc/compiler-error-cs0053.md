---
title: "컴파일러 오류 CS0053 | Microsoft Docs"
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
  - "CS0053"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0053"
ms.assetid: 62a96ef4-e8d2-44d0-9d39-5cd7a38efe52
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0053
일관성 없는 접근성: 'type' 속성 형식이 'property' 속성보다 액세스하기 어렵습니다.  
  
 공용 구문은 공개적으로 액세스 가능한 개체를 반환해야 합니다. 자세한 내용은 [액세스 한정자](/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)을 참조하세요.  
  
 다음 샘플에서는 CS0053을 생성합니다.  
  
```  
// CS0053.cs class MyClass //defaults to private accessibility // try the following line instead // public class MyClass { } public class MyClass2 { public MyClass myProperty   // CS0053 { get { return new MyClass(); } set { } } } public class MyClass3 { public static void Main() { } }  
```