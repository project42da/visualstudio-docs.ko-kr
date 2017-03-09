---
title: "컴파일러 오류 CS0708 | Microsoft Docs"
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
  - "CS0708"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0708"
ms.assetid: 19e1907f-b78c-4c8b-b78c-eedfd57115f2
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0708
'field': 정적 클래스에 인스턴스 멤버를 선언할 수 없습니다.  
  
 이 오류는 정적으로 선언된 클래스에서 비정적 멤버를 선언하는 경우에 발생합니다. 정적 클래스의 인스턴스를 생성할 수 없으므로 인스턴스 변수는 의미가 없습니다.**static** 키워드는 정적 클래스의 모든 멤버에 적용해야 합니다.  
  
 다음 샘플에서는 CS0708을 생성합니다.  
  
```  
// CS0708.cs // compile with: /target:library public static class C { int i;  // CS0708 static int j;  // OK }  
```