---
title: "컴파일러 오류 CS0020 | Microsoft Docs"
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
  - "CS0020"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0020"
ms.assetid: 7a54db39-6530-4e34-aa17-a90f85223d08
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0020
상수 0으로 나누었습니다.  
  
 식에서 나누기 연산의 분모에 리터럴\(변수 아님\) 값 0을 사용합니다. 0으로 나누기는 정의되지 않았으므로 사용할 수 없습니다.  
  
 다음 샘플에서는 CS0020을 생성합니다.  
  
```  
// CS0020.cs namespace x { public class b { public static void Main() { 1 / 0;   // CS0020 } } }  
```  
  
## 참고 항목  
 [연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/operators)