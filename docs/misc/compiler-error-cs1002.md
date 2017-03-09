---
title: "컴파일러 오류 CS1002 | Microsoft Docs"
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
  - "CS1002"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1002"
ms.assetid: 659b7abf-9311-40c9-9594-5372464c6148
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1002
;이 필요합니다.  
  
 컴파일러에서 세미콜론 누락을 발견했습니다. C\#에서는 모든 문의 끝에 세미콜론이 필요합니다. 문이 둘 이상의 줄에 걸쳐 있을 수 있습니다.  
  
 다음 샘플에서는 CS1002를 생성합니다.  
  
```  
// CS1002.cs namespace x { abstract public class clx { int i   // CS1002, missing semicolon public static int Main() { return 0; } } }  
```  
  
## 참고 항목  
 [문](/dotnet/csharp/programming-guide/statements-expressions-operators/statements)