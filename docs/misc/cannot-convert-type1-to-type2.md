---
title: "&#39;type1&#39;을 &#39;type2&#39;로 변환할 수 없습니다. | Microsoft Docs"
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
  - "bc31193"
  - "vbc31193"
helpviewer_keywords: 
  - "BC31193"
ms.assetid: f25a9f5b-7741-4cd6-b85a-b19037ed8e49
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;type1&#39;을 &#39;type2&#39;로 변환할 수 없습니다.
'type1'을 'type2'로 변환할 수 없습니다. 'Value' 속성을 사용하여 'parentElement'의 첫 번째 요소의 문자열 값을 가져올 수 있습니다.  
  
 XML 리터럴을 특정 형식으로 암시적으로 캐스팅하려고 했습니다. XML 리터럴은 지정된 형식으로 암시적으로 캐스팅할 수 없습니다.  
  
 **오류 ID:** BC31193  
  
### 이 오류를 해결하려면  
  
-   XML 리터럴의 `Value` 속성을 사용하여 해당 값을 `String`으로 참조합니다.`CType` 함수, 다른 형식 변환 함수 또는 <xref:System.Convert> 클래스를 사용하여 지정된 형식으로 값을 캐스팅합니다.  
  
## 참고 항목  
 <xref:System.Convert>   
 [Accessing XML in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/xml/accessing-xml)   
 [Type Conversion Functions](/dotnet/visual-basic/language-reference/functions/type-conversion-functions)   
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)