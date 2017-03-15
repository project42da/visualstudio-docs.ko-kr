---
title: "컴파일러 오류 CS0277 | Microsoft Docs"
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
  - "CS0277"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0277"
ms.assetid: 8abec3eb-4d4c-4aab-87cc-d0444ab23535
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0277
'class'는 'accessor' 인터페이스 멤버를 구현하지 않습니다. 'class accessor'가 public이 아닙니다.  
  
 인터페이스의 속성을 구현하려고 하지만 클래스의 속성 접근자 구현이 public이 아닌 경우 이 오류가 발생합니다. 인터페이스 멤버를 구현하는 메서드에는 public 접근성이 있어야 합니다. 이 문제를 해결하려면 속성 접근자에서 액세스 한정자를 제거합니다.  
  
## 예제  
 다음 예제는 CS0277을 생성합니다.  
  
```  
// CS0277.cs public interface MyInterface { int Property { get; set; } } public class MyClass : MyInterface   // CS0277 { public int Property { get { return 0; } // Try this instead: //set { } protected set { } } }  
```