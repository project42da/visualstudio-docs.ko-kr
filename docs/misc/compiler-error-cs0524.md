---
title: "컴파일러 오류 CS0524 | Microsoft Docs"
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
  - "CS0524"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0524"
ms.assetid: a5cd8fb0-f5df-4580-9116-a6be4dffd1cb
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0524
'type': 인터페이스는 형식을 선언할 수 없습니다.  
  
 [interface](/dotnet/csharp/language-reference/keywords/interface)에는 사용자 정의 형식을 포함할 수 없으며 메서드 및 속성만 포함해야 합니다.  
  
## 예제  
 다음 샘플에서는 CS0524를 생성합니다.  
  
```  
// CS0524.cs public interface Clx { public class Cly   // CS0524, delete user-defined type { } }  
  
```