---
title: "컴파일러 오류 CS1715 | Microsoft Docs"
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
  - "CS1715"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1715"
ms.assetid: 740044d1-a61c-4156-bc6a-adf26c7499ec
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1715
'Type1': 형식이 재정의된 'Member Name' 멤버와 일치하려면 'Type2'여야 합니다.  
  
 이 오류는 [컴파일러 오류 CS0508](../misc/compiler-error-cs0508.md)과 동일합니다. 단, CS0508은 이제 반환 형식이 있는 메서드에만 적용되고, CS1715는 'return types' 대신 'types'만 있는 속성 및 인덱서에 적용됩니다.  
  
## 예제  
 다음 코드에서는 CS1715를 생성합니다.  
  
```  
// CS1715.cs abstract public class Base { abstract public int myProperty { get; set; } } public class Derived : Base { int myField; public override double myProperty  // CS1715 // try the following line instead // public override int myProperty { get { return myField; } set { myField;= value; } } public static void Main() { Derived d = new Derived(); d.myProperty = 5; } }  
```