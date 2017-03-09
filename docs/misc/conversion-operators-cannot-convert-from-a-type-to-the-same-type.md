---
title: "변환 연산자는 특정 형식에서 동일한 형식으로 변환할 수 없습니다. | Microsoft Docs"
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
  - "bc33024"
  - "vbc33024"
helpviewer_keywords: 
  - "BC33024"
ms.assetid: 4b47bcb0-4f0c-4d1c-9274-cce5b8e2b370
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 변환 연산자는 특정 형식에서 동일한 형식으로 변환할 수 없습니다.
매개 변수 및 반환 둘 다에 동일한 형식을 사용하여 변환 연산자를 선언했습니다.  
  
 형식을 자체 형식으로 변환하는 것은 의미가 없습니다.  
  
 **오류 ID:** BC33024  
  
### 이 오류를 해결하려면  
  
-   매개 변수 또는 반환 값의 형식을 변경합니다. 둘 중 하나는 이 연산자가 정의된 클래스 또는 구조체의 형식이어야 합니다. 다른 하나는 다른 형식이어야 합니다.  
  
-   매개 변수의 내용을 변환해야 하는 경우 연산자 대신 [Function Statement](/dotnet/visual-basic/language-reference/statements/function-statement)을 사용하여 `Function` 프로시저를 정의합니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)