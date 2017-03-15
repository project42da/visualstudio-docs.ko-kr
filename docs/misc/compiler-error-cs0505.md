---
title: "컴파일러 오류 CS0505 | Microsoft Docs"
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
  - "CS0505"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0505"
ms.assetid: e3cb9e33-7338-4869-859b-81d7439f0d23
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0505
'member1': 'member2'가 함수가 아니므로 재정의할 수 없습니다.  
  
 클래스를 선언할 때 기본 클래스에서 메서드가 아닌 것을 재정의하려고 했습니다. 재정의는 멤버 유형과 일치해야 합니다. 기본 클래스의 메서드로 동일한 이름이 있는 메서드를 사용하려면 기본 클래스의 메서드 선언에서 [새로 만들기](/dotnet/csharp/language-reference/keywords/new)를 사용합니다\([재정의](/dotnet/csharp/language-reference/keywords/override) 사용 안 함\).  
  
 다음 샘플에서는 CS0505를 생성합니다.  
  
```  
// CS0505.cs // compile with: /target:library public class clx { public int i; } public class cly : clx { public override int i() { return 0; }   // CS0505 }  
```