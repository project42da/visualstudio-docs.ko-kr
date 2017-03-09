---
title: "컴파일러 오류 CS1107 | Microsoft Docs"
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
  - "CS1107"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1107"
ms.assetid: 1b6f6790-53af-4261-a14f-bf2db9790f0b
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1107
매개 변수에는 'modifier name' 한정자 하나만 사용할 수 있습니다.  
  
 `this`, `ref` 및 `out`과 같은 매개 변수 한정자가 매개 변수 정의에서 두 번 이상 나타나는 것은 오류입니다.  
  
## 예제  
 다음 예제에서는 CS1107을 생성합니다.  
  
```  
// cs1107.cs public static class Test { // Extension methods. public static void TestMethod(this this t) {} // CS1107 // Regular Instance Method public void TestMethod(ref ref int i) {} // CS1107 }  
```