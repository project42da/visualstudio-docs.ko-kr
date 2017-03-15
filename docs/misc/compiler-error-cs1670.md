---
title: "컴파일러 오류 CS1670 | Microsoft Docs"
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
  - "CS1670"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1670"
ms.assetid: ee2507e5-b509-4af3-a15e-2c1f2da7159c
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1670
이 컨텍스트에서는 params가 유효하지 않습니다.  
  
 많은 C\# 기능이 가변 인수 목록과 호환되지 않으며 다음을 포함하여 `params```키워드를 허용하지 않습니다.  
  
-   무명 메서드의 매개 변수 목록  
  
-   오버로드된 연산자  
  
## 예제  
 다음 샘플에서는 CS1670을 생성합니다.  
  
```  
// CS1670.cs public class C { public bool operator +(params int[] paramsList)  // CS1670 { return false; } static void Main() { } }  
```