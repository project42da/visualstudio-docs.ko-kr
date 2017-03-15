---
title: "XML 리터럴은 괄호로 묶어야만 여기에 표시할 수 있습니다. | Microsoft Docs"
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
  - "bc31198"
  - "vbc31198"
helpviewer_keywords: 
  - "BC31198"
ms.assetid: 97b16076-39ff-430a-9c65-073d01bcb08e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML 리터럴은 괄호로 묶어야만 여기에 표시할 수 있습니다.
XML 리터럴 선언이 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러가 인식할 수 없는 식의 위치에 사용되었습니다. 즉, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러에서 보다 작음\(\<\) 문자가 비교 연산자로 사용되었는지 또는 XML 리터럴의 시작 부분으로 사용되었는지 확인할 수 없습니다. 다음 코드는 예제를 제공합니다.  
  
 \[Visual Basic\]  
  
```  
' Generates an error. Dim queryResult = From element In elements _ Where <sample>Value</sample> = "Value" _ Select element  
```  
  
 **오류 ID:** BC31198  
  
### 이 오류를 해결하려면  
  
-   다음 예제와 같이 XML 리터럴 선언을 괄호로 묶습니다.  
  
    ```vb#  
    Dim queryResult = From element In elements _ Where (<sample> Value</sample>) = "Value" _ Select element  
    ```  
  
-   다음 예제와 같이 기존 XML 리터럴을 가리키도록 코드를 수정합니다.  
  
    ```vb#  
    Dim queryResult = From element In elements _ Where e.<sample>.Value = "Value" _ Select element  
    ```  
  
## 참고 항목  
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [XML Axis Properties](/dotnet/visual-basic/language-reference/xml-axis/xml-axis-properties)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)