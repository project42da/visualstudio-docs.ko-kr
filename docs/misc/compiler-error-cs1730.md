---
title: "컴파일러 오류 CS1730 | Microsoft Docs"
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
  - "CS1730"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1730"
ms.assetid: 20900ca0-702f-4f35-9a60-2dee9cb11902
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1730
using 절과 extern 별칭 선언을 제외하고 어셈블리 특성과 모듈 특성은 파일에 정의된 다른 모든 요소보다 앞에 와야 합니다.  
  
 어셈블리 수준에서 적용된 특성은 형식 정의 뒤에 나타날 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  특성을 파일 맨 위의 `using` 지시문 및 `extern` 별칭 선언 아래로 이동합니다.  
  
## 예제  
 다음 코드에서는 CS1730을 생성합니다.  
  
```  
// cs1730.cs class Test { } [assembly: System.Attribute] // CS1730  
```  
  
## 참고 항목  
 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)