---
title: "변환 연산자는 Object로 변환할 수 없습니다. | Microsoft Docs"
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
  - "bc33028"
  - "vbc33028"
helpviewer_keywords: 
  - "BC33028"
ms.assetid: 064b478c-85a1-4e13-a292-d8aebb079cad
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 변환 연산자는 Object로 변환할 수 없습니다.
변환 연산자가 [Object Data Type](/dotnet/visual-basic/language-reference/data-types/object-data-type)의 반환 형식으로 선언되었습니다.  
  
 컴파일 시간에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]은 모든 참조 형식이 해당 상속 계층 구조의 형식으로, 즉 파생하는 형식 또는 파생된 형식으로 변환되도록 미리 정의되어 있다고 간주합니다.`Object`는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에서 유니버설 데이터 형식이므로 모든 형식이 `Object`에서 파생됩니다.  
  
 컴파일러에서는 이 변환이 이미 정의되어 있다고 간주하므로 다시 정의할 수 없습니다.  
  
 **오류 ID:** BC33028  
  
### 이 오류를 해결하려면  
  
-   이 연산자 정의를 완전히 제거합니다. 이미 미리 정의되어 있습니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [유니버설 데이터 형식 개체\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/5315bf21-2b22-45ab-98cd-5631dffbcb2f)