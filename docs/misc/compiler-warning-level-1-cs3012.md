---
title: "컴파일러 경고(수준 1) CS3012 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS3012"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3012"
ms.assetid: 1f7555b4-61e4-4821-85c9-586301df4c5c
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3012
어셈블리의 CLSCompliant 특성과 다른 모듈의 CLSCompliant 특성을 지정할 수 없습니다.  
  
 `[module:System.CLCSompliant(true)]`를 통해 모듈이 CLS\(공용 언어 사양\)를 준수하려면 [\/target: module](../Topic/-target:module%20\(C%23%20Compiler%20Options\).md) 컴파일러 옵션을 사용하여 빌드되어야 합니다. CLS에 대한 자세한 내용은 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)를 참조하세요.  
  
## 예제  
 다음 예제는 `/target:module` 없이 빌드될 때 CS3012를 생성합니다.  
  
```  
// CS3012.cs // compile with: /W:1 [module:System.CLSCompliant(true)]   // CS3012 public class C { public static void Main() { } }  
```