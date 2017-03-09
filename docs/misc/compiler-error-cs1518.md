---
title: "컴파일러 오류 CS1518 | Microsoft Docs"
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
  - "CS1518"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1518"
ms.assetid: 26e0870d-fe91-4c66-b3f8-ed2b074c964e
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1518
클래스, 대리자, 열거형, 인터페이스 또는 구조체가 필요합니다.  
  
 [네임스페이스](/dotnet/csharp/language-reference/keywords/namespace)에서 지원되지 않는 선언을 찾았습니다. 네임스페이스 내에서 컴파일러는 클래스, 구조체, 열거형, 인터페이스, 네임스페이스 및 대리자만 허용합니다.  
  
## 예제  
 다음 샘플에서는 CS1518을 생성합니다.  
  
```  
// CS1518.cs namespace x { sealed class c1 {};      // OK namespace f2 {};         // OK sealed f3 {};            // CS1518 }  
```