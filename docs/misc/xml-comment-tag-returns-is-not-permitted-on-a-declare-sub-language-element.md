---
title: "XML 주석 태그 &#39;returns&#39;는 &#39;declare sub&#39; 언어 요소에서 사용할 수 없음 | Microsoft Docs"
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
  - "bc42315"
  - "vbc42315"
helpviewer_keywords: 
  - "BC42315"
ms.assetid: 55ba3e8a-ba7f-42e3-a4a7-b22844e72564
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML 주석 태그 &#39;returns&#39;는 &#39;declare sub&#39; 언어 요소에서 사용할 수 없음
XML 주석 태그 'returns'는 'declare sub' 언어 요소에서 사용할 수 없습니다. XML 주석이 무시됩니다.  
  
 `Declare Sub` 선언에 대한 XML 주석에는 `<`returns`>` 태그를 포함할 수 없습니다.  
  
 **오류 ID:** BC42315  
  
### 이 오류를 해결하려면  
  
-   지원되지 않는 `<`returns`>` 태그를 제거합니다.  
  
## 참고 항목  
 [\<returns\>](../Topic/%3Creturns%3E%20\(Visual%20Basic\).md)   
 [XML Comment Tags](/dotnet/visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments)   
 [Documenting Your Code with XML](/dotnet/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml)   
 [Declare Statement](/dotnet/visual-basic/language-reference/statements/declare-statement)