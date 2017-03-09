---
title: "모듈에는 연산자를 선언할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc33018"
  - "vbc33018"
helpviewer_keywords: 
  - "BC33018"
ms.assetid: 10a8fd2d-2af7-4f90-9f2a-50c07ebf7589
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 모듈에는 연산자를 선언할 수 없습니다.
[Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)이 모듈 정의에 나타납니다.  
  
 정의하는 클래스 또는 구조체의 일부로 연산자를 정의할 수 있습니다. 연산자는 해당 클래스 또는 구조체를 피연산자 중 하나 이상으로 사용해야 합니다.  
  
 연산자는 프로그래밍 요소의 인스턴스를 피연산자 중 하나로 사용해야 하며 클래스와 구조체만 인스턴스를 포함합니다. 따라서 다른 프로그래밍 요소의 일부로 연산자를 정의할 수 없습니다.  
  
 **오류 ID:** BC33018  
  
### 이 오류를 해결하려면  
  
-   모듈에 대한 연산이 필요한 [Function Statement](/dotnet/visual-basic/language-reference/statements/function-statement)을 사용하여 연산을 수행하는 `Function` 프로시저를 정의합니다.  
  
-   모듈 내에서 클래스 또는 구조체를 정의하고 해당 클래스 또는 구조체에서 연산자를 정의할 수도 있습니다. 그러나 연산자는 해당 클래스 또는 구조체 인스턴스를 피연산자 중 하나 이상으로 사용해야 합니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)