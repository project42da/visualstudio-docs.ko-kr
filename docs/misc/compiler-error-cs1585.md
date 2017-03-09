---
title: "컴파일러 오류 CS1585 | Microsoft Docs"
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
  - "CS1585"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1585"
ms.assetid: 429268c3-2dae-4c71-9e0d-be1badb3ca68
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1585
'keyword' 멤버 한정자는 멤버 형식과 이름 앞에 와야 합니다.  
  
 메서드 서명의 액세스 지정자가 올바른 위치에서 사용되지 않았습니다.  
  
 다음 샘플에서는 CS1585를 생성합니다.  
  
```  
// CS1585.cs public class Class1 { public void static Main(string[] args)   // CS1585 // try the following line instead // public static void Main(string[] args) { } }  
```