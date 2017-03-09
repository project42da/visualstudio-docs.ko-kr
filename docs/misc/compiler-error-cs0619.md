---
title: "컴파일러 오류 CS0619 | Microsoft Docs"
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
  - "CS0619"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0619"
ms.assetid: a2060eb1-cda5-493c-b049-9b1792f88207
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0619
'member'는 사용되지 않습니다. 'text'  
  
 클래스 멤버가 [Obsolete](http://msdn.microsoft.com/ko-kr/05e99cd0-bda6-4f79-a890-1ca093b4b488) 특성으로 표시되어 클래스 멤버를 참조할 때 오류가 발생합니다.  
  
 다음 샘플에서는 CS0619를 생성합니다.  
  
```  
// CS0619.cs using System; public class C { [Obsolete("Use newMethod instead", true)]   // generates an error on use public static void m() { } // this is the method you should be using public static void newMethod() { } } class MyClass { public static void Main() { C.m();   // CS0619 } }  
```