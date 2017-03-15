---
title: "컴파일러 오류 CS0553 | Microsoft Docs"
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
  - "CS0553"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0553"
ms.assetid: d2d6ddb1-9294-4e85-83d8-c35bd7a70f5b
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0553
'conversion routine': 사용자가 기본 클래스로\/에서의 변환을 정의했습니다.  
  
 기본 클래스 값으로의 사용자 정의 변환은 허용되지 않습니다. 이러한 연산자는 필요하지 않습니다.  
  
 다음 샘플에서는 CS0553을 생성합니다.  
  
```  
// CS0553.cs namespace x { public class ii { } public class a : ii { // delete the conversion routine to resolve CS0553 public static implicit operator ii(a aa) // CS0553 { return new ii(); } public static void Main() { } } }  
```