---
title: "변환 연산자는 인터페이스 형식에서 변환할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc33029"
  - "bc33029"
helpviewer_keywords: 
  - "BC33029"
ms.assetid: 0d0ee461-dd48-424b-b83a-484bfc648d4d
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 변환 연산자는 인터페이스 형식에서 변환할 수 없습니다.
매개 변수에 인터페이스 형식을 사용하여 변환 연산자를 선언했습니다.  
  
 컴파일 시간에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]은 인터페이스에서 참조 형식으로 미리 정의된 변환이 있는 것으로 간주합니다. 이러한 변환은 런타임에 실패할 수 있지만 컴파일러에서 런타임 결과를 예측할 수 없으므로 이러한 변환의 컴파일을 허용합니다.  
  
 컴파일러에서는 이 변환이 이미 정의되어 있다고 간주하므로 다시 정의할 수 없습니다.  
  
 **오류 ID:** BC33029  
  
### 이 오류를 해결하려면  
  
-   이 연산자 정의를 완전히 제거합니다. 이미 미리 정의되어 있습니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)