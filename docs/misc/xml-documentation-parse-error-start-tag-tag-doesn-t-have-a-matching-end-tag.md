---
title: "XML 문서 구문 분석 오류: &#39;&lt;tag&gt;&#39; 시작 태그에 짝이 되는 끝 태그가 없습니다. | Microsoft Docs"
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
  - "vbc42316"
  - "BC42316"
helpviewer_keywords: 
  - "BC42316"
ms.assetid: 45b68176-ebf6-43af-820e-6801aabb6c57
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML 문서 구문 분석 오류: &#39;&lt;tag&gt;&#39; 시작 태그에 짝이 되는 끝 태그가 없습니다.
XML 문서 구문 분석 오류: \<tag\> 시작 태그에 짝이 되는 끝 태그가 없습니다. XML 주석이 무시됩니다.  
  
 XML 주석이 시작 태그를 포함하지만 일치하는 끝 태그를 포함하지 않습니다.  
  
 **오류 ID:** BC42316  
  
### 이 오류를 해결하려면  
  
-   시작 태그와 일치하는 끝 태그를 추가합니다.  
  
     — 또는 —  
  
-   태그에 [\<seealso\>](../Topic/%3Cseealso%3E%20\(Visual%20Basic\).md)와 같은 내부 텍스트가 포함되지 않은 경우 닫는 꺾쇠 괄호 앞에 슬래시를 지정합니다.  
  
## 참고 항목  
 [XML Comment Tags](/dotnet/visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments)   
 [Documenting Your Code with XML](/dotnet/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml)