---
title: "컴파일러 오류 CS0059 | Microsoft Docs"
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
  - "CS0059"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0059"
ms.assetid: 25a8624b-7f7b-4487-ba80-413d57f9132b
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0059
일관성 없는 접근성: 'type' 매개 변수 형식이 'delegate' 대리자보다 액세스하기 어렵습니다.  
  
 반환 형식 및 메서드의 정식 매개 변수 목록에서 참조된 각 형식은 적어도 메서드 자체만은 액세스할 수 있어야 합니다. 자세한 내용은 [액세스 한정자](/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0059를 생성합니다.  
  
```  
// CS0059.cs class MyClass //defaults to private accessibility // try the following line instead // public class MyClass { } public delegate void MyClassDel( MyClass myClass);   // CS0059 public class Program { public static void Main() { } }  
```