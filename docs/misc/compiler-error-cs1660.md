---
title: "컴파일러 오류 CS1660 | Microsoft Docs"
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
  - "CS1660"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1660"
ms.assetid: ae7fede3-471b-4e20-97a7-b80fdc2bb080
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1660
무명 메서드 블록이 대리자 형식이 아니므로 'type' 형식으로 변환할 수 없습니다.  
  
 이 오류는 무명 메서드 블록을 대리자 형식이 아닌 형식에 할당하거나 변환하려고 하는 경우 발생합니다.  
  
 다음 샘플에서는 CS1660을 생성합니다.  
  
```  
// CS1660.cs delegate int MyDelegate(); class C { static void Main() { int i = delegate { return 1; };  // CS1660 // Try this instead: // MyDelegate myDelegate = delegate { return 1; }; // int i = myDelegate(); } }  
```