---
title: "컴파일러 오류 CS0551 | Microsoft Docs"
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
  - "CS0551"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0551"
ms.assetid: fb456ecf-dff3-4e39-b9b3-de23d81dadea
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0551
'implementation' 명시적 인터페이스 구현에 'accessor' 접근자가 누락되었습니다.  
  
 명시적으로 인터페이스 속성을 구현하는 클래스는 인터페이스가 정의하는 모든 접근자를 구현해야 합니다.  
  
 자세한 내용은 [속성 사용](/dotnet/csharp/programming-guide/classes-and-structs/using-properties)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0551을 생성합니다.  
  
```  
// CS0551.cs // compile with: /target:library interface ii { int i { get; set; } } public class a : ii { int ii.i { set {} }   // CS0551 // OK int ii.i { set {} get { return 0; } } }  
```