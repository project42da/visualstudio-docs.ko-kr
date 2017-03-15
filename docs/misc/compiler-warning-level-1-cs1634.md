---
title: "컴파일러 경고(수준 1) CS1634 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1634"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1634"
ms.assetid: 4fd00eeb-89e3-4c18-827d-9b00a4bd8c9a
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1634
disable 또는 restore가 필요합니다.  
  
 이 오류는 disable 또는 restore가 생략된 경우와 같이 \#pragma 경고 절이 잘못 구성된 경우에 발생합니다. 자세한 내용은 [\#pragma 경고](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning) 항목을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS1634를 생성합니다.  
  
```  
// CS1634.cs // compile with: /W:1 #pragma warning   // CS1634 // Try this instead: // #pragma warning disable 0219 class MyClass { public static void Main() { } }  
```