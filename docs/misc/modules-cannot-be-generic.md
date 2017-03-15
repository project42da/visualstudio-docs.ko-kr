---
title: "모듈은 제네릭일 수 없습니다. | Microsoft Docs"
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
  - "BC32073"
  - "vbc32073"
helpviewer_keywords: 
  - "BC32073"
ms.assetid: 47246e2b-51d4-4a10-a3ac-bc77b44fa2ca
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 모듈은 제네릭일 수 없습니다.
`Module` 문은 `Of` 키워드를 사용하여 제네릭 형식 매개 변수를 도입합니다.  
  
 제네릭 클래스, 구조체, 인터페이스, 프로시저 및 대리자를 정의하고 사용할 수 있습니다. 제네릭 모듈은 정의할 수 없습니다.  
  
 **오류 ID:** BC32073  
  
### 이 오류를 해결하려면  
  
1.  `Module` 문에서 `Of` 키워드를 제거합니다.  
  
2.  제네릭 모듈의 기능을 사용하려는 경우 가장 유사한 항목은 제네릭 클래스입니다.`Module` 문 대신 [Class Statement](/dotnet/visual-basic/language-reference/statements/class-statement)를 사용합니다.  
  
## 참고 항목  
 [Module Statement](/dotnet/visual-basic/language-reference/statements/module-statement)   
 [Of](/dotnet/visual-basic/language-reference/statements/of-clause)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의](../Topic/How%20to:%20Define%20a%20Class%20That%20Can%20Provide%20Identical%20Functionality%20on%20Different%20Data%20Types%20\(Visual%20Basic\).md)