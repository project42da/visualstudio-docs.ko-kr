---
title: "식은 따옴표로 묶인 특성 값 내에 표시할 수 없습니다. | Microsoft Docs"
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
  - "bc31155"
  - "vbc31155"
helpviewer_keywords: 
  - "BC31155"
ms.assetid: ed3e618e-de94-4e4e-afaf-72b11073fb1d
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 식은 따옴표로 묶인 특성 값 내에 표시할 수 없습니다.
식은 따옴표로 묶인 특성 값 내에 표시할 수 없습니다. 따옴표를 제거하세요.  
  
 XML 리터럴에 대한 특성 값의 포함 식이 따옴표 안에 들어 있습니다.  
  
 **오류 ID:** BC31155  
  
### 이 오류를 해결하려면  
  
-   특성 값에서 구분 따옴표를 제거합니다. 예를 들면 다음과 같습니다.  
  
    ```vb#  
    ' Generates an error. Dim elem = <outer attr="<%= value %>" /> ' Does not generate an error. Dim elem = <outer attr=<%= value %> />  
    ```  
  
## 참고 항목  
 [Embedded Expressions in XML](/dotnet/visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml)   
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)