---
title: "컴파일러 오류 CS0143 | Microsoft Docs"
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
  - "CS0143"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0143"
ms.assetid: dfe6f6ba-dec9-49bd-9d5b-3dc4743bd940
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0143
'class' 형식에 정의된 생성자가 없습니다.  
  
 사용할 수 있는 적절한 기본 생성자가 없습니다. 이는 기본 제공 숫자 값 형식에 대한 경우로 값을 할당하면 초기화됩니다.  
  
 다음 샘플에서는 CS0143을 생성합니다.  
  
```  
// CS0143.cs class MyClass { static public void Main () { double d = new double(4.5);   // CS0143 // Try this line instead: // double d = 4.5; } }  
```