---
title: "컴파일러 오류 CS0683 | Microsoft Docs"
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
  - "CS0683"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0683"
ms.assetid: 04cca66d-8a0b-469a-b157-9c8ece368c48
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0683
'explicitmethod' 명시적 메서드 구현에서 'method'는 접근자이므로 구현할 수 없습니다.  
  
 다음 샘플에서는 CS0683을 생성합니다.  
  
```  
// CS0683.cs interface IExample { int Test { get; } } class CExample : IExample { int IExample.get_Test() { return 0; } // CS0683 int IExample.Test { get{ return 0; } } // correct }  
```