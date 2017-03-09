---
title: "컴파일러 경고(수준 3) CS0169 | Microsoft Docs"
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
  - "CS0169"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0169"
ms.assetid: 04b0015f-658d-440a-b9ba-831178f1a180
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 3) CS0169
전용 필드 'class member'가 사용되지 않습니다.  
  
 전용 변수가 선언되었지만 참조되지 않습니다. 이 경고를 생성하는 일반적인 방법은 클래스의 전용 멤버를 선언하고 사용하지 않는 경우입니다.  
  
 다음 샘플에서는 CS0169를 생성합니다.  
  
```  
// compile with: /W:3 using System; public class ClassX { int i;   // CS0169, i is not used anywhere public static void Main() { } }  
```