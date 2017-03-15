---
title: "연산자를 오버로드할 수 없습니다. | Microsoft Docs"
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
  - "vbc33002"
  - "bc33002"
helpviewer_keywords: 
  - "BC33002"
ms.assetid: 8628ea42-57d8-41ca-8bdc-5e4c27be543e
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연산자를 오버로드할 수 없습니다.
특정 연산자만 오버로드됩니다. 다음 표에는 정의할 수 있는 연산자가 나와 있습니다.  
  
|형식|연산자|  
|--------|---------|  
|단항|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|이항|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|변환\(단항\)|`CType`|  
  
 이진 목록의 `=` 연산자는 대입 연산자가 아닌 비교 연산자입니다.  
  
 **오류 ID:** BC33002  
  
### 이 오류를 해결하려면  
  
1.  오버로드할 수 있는 연산자 집합에서 연산자를 선택합니다.  
  
2.  직접 오버로드할 수 없는 연산자 오버로드 기능이 필요할 경우 적절한 매개 변수를 사용하고 적절한 값을 반환하는 `Function` 프로시저를 만듭니다.  
  
## 참고 항목  
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Function Statement](/dotnet/visual-basic/language-reference/statements/function-statement)