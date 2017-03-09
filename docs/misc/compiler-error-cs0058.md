---
title: "컴파일러 오류 CS0058 | Microsoft Docs"
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
  - "CS0058"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0058"
ms.assetid: 9535da60-03b9-41ab-93e1-e57b6440fca9
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0058
일관성 없는 접근성: 'type' 반환 형식이 'delegate' 대리자보다 액세스하기 어렵습니다.  
  
 공용 구문은 공개적으로 액세스 가능한 개체를 반환해야 합니다. 자세한 내용은 [액세스 한정자](/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)을 참조하세요.  
  
 다음 샘플에서는 액세스 한정자가 MyClass에 적용되지 않아서 기본적으로 private 접근성이 부여되기 때문에 CS0058을 생성합니다.  
  
```  
// CS0058.cs class MyClass // try the following line instead // public class MyClass { } public delegate MyClass MyClassDel();   // CS0058 public class A { public static void Main() { } }  
```  
  
## 참고 항목  
 [private](/dotnet/csharp/language-reference/keywords/private)