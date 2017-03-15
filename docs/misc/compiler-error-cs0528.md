---
title: "컴파일러 오류 CS0528 | Microsoft Docs"
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
  - "CS0528"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0528"
ms.assetid: 8f5dde55-7e4f-4ffa-be14-0e0f3a538118
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0528
'interface'가 이미 인터페이스 목록에 있습니다.  
  
 인터페이스 상속 목록이 중복을 포함합니다.[interface](/dotnet/csharp/language-reference/keywords/interface)는 상속 목록에서 한 번만 지정할 수 있습니다.  
  
 다음 샘플에서는 CS0528을 생성합니다.  
  
```  
// CS0528.cs namespace x { public interface a { } public class b : a, a   // CS0528 { public void Main() { } } }  
```