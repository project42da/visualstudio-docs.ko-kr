---
title: "컴파일러 오류 CS0836 | Microsoft Docs"
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
  - "CS0836"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0836"
ms.assetid: 74a12271-1612-45aa-a398-7964e0269892
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0836
상수 식에서는 무명 형식을 사용할 수 없습니다.  
  
 상수 식에 허용되는 항목은 명명된 상수, 리터럴 및 상수 식을 결합하는 수학 식뿐입니다.  
  
### 이 오류를 해결하려면  
  
1.  무명 형식을 명명된 형식으로 설정합니다.  
  
## 예제  
 다음 예제에서는 CS0836을 생성하는 한 가지 방법을 보여 줍니다.  
  
```  
// cs0836.cs using System; [AttributeUsage(AttributeTargets.Class, AllowMultiple = true, Inherited = false)] public class A : Attribute { public A(object obj) { } } [A(new { })] // CS0836 public class B { } public class Test { public static int Main() { return 0; } }  
```