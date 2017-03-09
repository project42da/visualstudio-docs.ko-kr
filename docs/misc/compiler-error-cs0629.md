---
title: "컴파일러 오류 CS0629 | Microsoft Docs"
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
  - "CS0629"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0629"
ms.assetid: 20f22ef0-3c6f-4108-ab09-3f0752375a10
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0629
'member' 조건부 멤버는 'Type Name' 형식으로 'base class member' 인터페이스 멤버를 구현할 수 없습니다.  
  
 [조건부](http://msdn.microsoft.com/ko-kr/e1c4913b-74d0-421a-8a6d-c14b3f0e68fb) 특성은 인터페이스의 구현에서 사용할 수 없습니다.  
  
 다음 샘플에서는 CS0629를 생성합니다.  
  
```  
// CS0629.cs interface MyInterface { void MyMethod(); } public class MyClass : MyInterface { [System.Diagnostics.Conditional("debug")] public void MyMethod()    // CS0629, remove the Conditional attribute { } public static void Main() { } }  
```