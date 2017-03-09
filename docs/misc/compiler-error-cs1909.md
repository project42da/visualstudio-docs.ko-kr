---
title: "컴파일러 오류 CS1909 | Microsoft Docs"
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
  - "CS1909"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1909"
ms.assetid: d465a107-0911-4440-8b3a-1e5dea6fda3c
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1909
DefaultValue 특성은 'type' 형식의 매개 변수에 사용할 수 없습니다.  
  
 CS1909는 매개 변수 형식에 적용할 수 없는 `DefaultValue` 특성을 사용할 때 생성됩니다.  
  
## 예제  
 다음 샘플에서는 CS1909를 생성합니다.  
  
```  
// CS1909.cs // compile with: /target:library using System.Runtime.InteropServices; public interface ISomeInterface { void Test1([DefaultParameterValue(new int[] {1, 2})] int[] arr1);   // CS1909 void Test2([DefaultParameterValue("Test String")] string s);   // OK }  
```