---
title: "컴파일러 오류 CS0503 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0503"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0503"
ms.assetid: 12a337c9-8c5d-473d-8ce6-057b2c7e7935
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0503
'method' 추상 메서드는 virtual로 표시할 수 없습니다.  
  
 **abstract**는 **virtual**을 암시하므로 멤버 메서드를 [abstract](/dotnet/csharp/language-reference/keywords/abstract) 및 [virtual](/dotnet/csharp/language-reference/keywords/virtual) 둘 다로 표시하는 것은 중복입니다.  
  
 다음 샘플에서는 CS0503을 생성합니다.  
  
```  
// CS0503.cs namespace x { abstract public class clx { abstract virtual public void f();   // CS0503 } }  
```