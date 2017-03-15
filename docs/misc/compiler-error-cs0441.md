---
title: "컴파일러 오류 CS0441 | Microsoft Docs"
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
  - "CS0441"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0441"
ms.assetid: 3f07500a-d479-424c-a0f4-c219be1b5a45
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0441
'class': 클래스는 static이면서 sealed일 수 없습니다.  
  
 이 오류는 static이면서 sealed인 클래스를 선언하는 경우에 발생합니다. static 클래스는 기본적으로 sealed이므로 sealed 한정자가 필요하지 않습니다. 해결하려면 한정자를 하나만 사용합니다.  
  
 다음 예제에서는 CS0441을 생성합니다.  
  
```  
// CS0441.cs sealed static class MyClass { }   // CS0441  
```