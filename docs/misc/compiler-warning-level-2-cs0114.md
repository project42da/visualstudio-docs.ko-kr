---
title: "컴파일러 경고(수준 2) CS0114 | Microsoft Docs"
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
  - "CS0114"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0114"
ms.assetid: 9647772b-d581-4620-981e-f9c607d4a1af
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0114
'function1'은 상속된 멤버 'function2'를 숨깁니다. 현재 메서드가 해당 구현을 재정의하도록 하려면 override 키워드를 추가하세요. 그렇지 않으면 new 키워드를 추가하세요.  
  
 클래스의 선언이 기본 클래스의 선언과 충돌하여 기본 클래스 멤버가 숨겨집니다.  
  
 자세한 내용은 [base](/dotnet/csharp/language-reference/keywords/base)를 참조하세요.  
  
 다음 샘플에서는 CS0114를 생성합니다.  
  
```  
// CS0114.cs // compile with: /W:2 /warnaserror abstract public class clx { public abstract void f(); } public class cly : clx { public void f() // CS0114, hides base class member // try the following line instead // override public void f() { } public static void Main() { } }  
```