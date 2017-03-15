---
title: "컴파일러 오류 CS0439 | Microsoft Docs"
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
  - "CS0430"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0439"
ms.assetid: 5cbac869-1b1b-45f9-98c8-38c17348035f
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0439
extern 별칭 선언은 네임스페이스에 정의된 다른 모든 요소보다 앞에 와야 합니다.  
  
 이 오류는 `extern` 선언이 `using` 선언과 같이 동일한 네임스페이스에서 다른 어떤 것 뒤에 나올 때 발생합니다.`extern` 선언은 다른 모든 네임스페이스 요소 앞에 와야 합니다.  
  
## 예제  
 다음 예제에서는 CS0439를 생성합니다.  
  
```  
// CS0439.cs using System; extern alias MyType;   // CS0439 // To resolve the error, make the extern alias the first line in the file. public class Test { public static void Main() { } }  
```