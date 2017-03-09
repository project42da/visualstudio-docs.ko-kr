---
title: "이 단항 연산자의 매개 변수 형식은 포함하는 형식 &#39;&lt;typename&gt;&#39;이어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc33020"
  - "bc33020"
helpviewer_keywords: 
  - "BC33020"
ms.assetid: 9c2c2c5b-6f18-49d2-bd6e-e735a6bced77
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이 단항 연산자의 매개 변수 형식은 포함하는 형식 &#39;&lt;typename&gt;&#39;이어야 합니다.
단항 연산자의 정의에서 연산자가 정의된 구조체 또는 클래스의 형식과는 다른 형식의 매개 변수를 지정합니다.  
  
 클래스 또는 구조체에서 연산자를 정의할 때 매개 변수 중 하나 이상은 해당 클래스 또는 구조체의 형식이어야 합니다. 단항 연산자의 경우 유일한 피연산자는 해당 클래스 또는 구조체의 형식이어야 합니다.  
  
 **오류 ID:** BC33020  
  
### 이 오류를 해결하려면  
  
-   매개 변수 형식을 연산자가 정의된 클래스 또는 구조체의 형식으로 변경합니다.  
  
-   한 데이터 형식을 매개 변수로 사용하고 다른 데이터 형식을 작업 결과로 반환하려는 경우 대신 변환 연산자를 정의합니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)