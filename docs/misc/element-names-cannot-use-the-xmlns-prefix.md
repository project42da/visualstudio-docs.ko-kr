---
title: "요소 이름에는 &#39;xmlns&#39; 접두사를 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc31189"
  - "bc31189"
helpviewer_keywords: 
  - "BC31189"
ms.assetid: 88716bb5-6766-4180-b2ed-1d1bee0ff7a6
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 요소 이름에는 &#39;xmlns&#39; 접두사를 사용할 수 없습니다.
XML 요소 리터럴이 XML 네임스페이스 접두사 `xmlns`로 지정되었습니다. 예:  
  
```vb#  
Dim elem = <xmlns:ElementName>  
```  
  
 XML 1.0 사양은 `xmlns`를 예약어로 식별합니다.  
  
 **오류 ID:** BC31189  
  
### 이 오류를 해결하려면  
  
-   XML 네임스페이스 접두사를 유효한 값으로 변경하거나 접두사를 제거합니다.  
  
## 참고 항목  
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [Imports Statement \(XML Namespace\)](/dotnet/visual-basic/language-reference/statements/imports-statement-xml-namespace)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)