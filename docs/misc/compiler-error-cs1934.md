---
title: "컴파일러 오류 CS1934 | Microsoft Docs"
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
  - "CS1934"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1934"
ms.assetid: 18624be3-d534-4695-bafd-cc664fcde15e
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1934
소스 형식 'type'에 대해 구현된 쿼리 패턴을 찾을 수 없습니다. 'method'를 찾을 수 없습니다. 범위 변수 'name'의 형식을 명시적으로 지정합니다.  
  
 이 오류는 쿼리 식이 표준 쿼리 연산자가 구현되지 않는 데이터 원본을 지정하는 경우에 발생합니다. 또는 범위 변수에 대해 명시적 형식을 지정하지 않고 `ArrayList`를 지정하는 경우에도 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  다음 예제에서의 해결 방법은 범위 변수의 형식을 지정하는 것입니다.  
  
    ```  
    var q = from int x in list  
    ```  
  
## 예제  
 다음 예제에서는 CS1934가 발생하는 경우를 보여 줍니다.  
  
```  
// cs1934.cs using System.Linq; using System.Collections; static class Test { public static void Main() { var list = new ArrayList { 0, 1, 2, 3, 4, 5 }; var q = from x in list // CS1934 select x + 1; } }  
```  
  
## 참고 항목  
 [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md)