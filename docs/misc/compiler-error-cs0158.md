---
title: "컴파일러 오류 CS0158 | Microsoft Docs"
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
  - "CS0158"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0158"
ms.assetid: 88ac61a9-ce55-4272-9141-0873765a7034
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0158
'label' 레이블은 포함된 범위에서 같은 이름으로 다른 레이블을 숨깁니다.  
  
 내부 범위의 레이블은 외부 범위에서 같은 이름의 레이블을 숨깁니다. 자세한 내용은 [goto](/dotnet/csharp/language-reference/keywords/goto)을 참조하세요.  
  
 다음 샘플에서는 CS0158을 생성합니다.  
  
```  
// CS0158.cs namespace MyNamespace { public class MyClass { public static void Main() { goto lab1; lab1: { lab1: goto lab1;   // CS0158 } } } }  
```