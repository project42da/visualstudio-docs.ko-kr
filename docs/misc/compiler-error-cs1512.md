---
title: "컴파일러 오류 CS1512 | Microsoft Docs"
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
  - "CS1512"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1512"
ms.assetid: 50740d85-598d-478f-bfe3-e8c2e1a02ab8
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1512
'base' 키워드는 현재 컨텍스트에서 사용할 수 없습니다.  
  
 [base](/dotnet/csharp/language-reference/keywords/base) 키워드가 메서드, 속성 또는 생성자 외부에서 사용되었습니다.  
  
 다음 예제에서는 CS1512를 생성합니다.  
  
```  
// CS1512.cs using System; class Base {} class CMyClass : Base { private String xx = base.ToString();   // CS1512 // Try putting this initialization in the constructor instead: // public CMyClass() // { //    xx = base.ToString(); // } public static void Main() { CMyClass z = new CMyClass(); } }  
```