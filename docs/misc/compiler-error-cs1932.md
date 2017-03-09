---
title: "컴파일러 오류 CS1932 | Microsoft Docs"
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
  - "CS1932"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1932"
ms.assetid: fc927899-2d35-4d47-9ae9-8fc99295bb66
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1932
'expression'을 범위 변수에 할당할 수 없습니다.  
  
 컴파일러가 `from` 절 또는 `let` 절에서 설명한 범위 변수의 형식을 유추할 수 있어야 합니다. 이는 null이 형식이 아니므로 null일 수 없으며 안전하지 않은 형식의 식으로 할당할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   잘못된 할당을 제거합니다.  
  
-   명시적으로 식을 허용되는 형식으로 캐스트  
  
## 예제  
 범위 변수의 형식을 유추할 수 없으므로 다음 코드에서는 CS1932를 생성합니다. 오류를 해결하려면 다음 예제와 같이 값을 지정된 형식으로 캐스트합니다.  
  
```  
// CS1932.cs using System.Linq; class Test { static void Main() { var x = from i in Enumerable.Range(1, 100) let k = null // CS1932 // Try the following line instead. let k = (string) null select i; } }  
```  
  
## 참고 항목  
 [LINQ 쿼리 식](/dotnet/csharp/programming-guide/linq-query-expressions/index)