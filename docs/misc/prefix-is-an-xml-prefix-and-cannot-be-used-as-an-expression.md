---
title: "&#39;prefix&#39;는 XML 접두사이므로 식으로 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30114"
  - "vbc30114"
helpviewer_keywords: 
  - "BC30114"
ms.assetid: 5cb7c89e-c61b-483a-9369-5285b7cbcf45
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;prefix&#39;는 XML 접두사이므로 식으로 사용할 수 없습니다.
'prefix'는 XML 접두사이므로 식으로 사용할 수 없습니다. 네임스페이스 개체를 만들려면 GetXmlNamespace 연산자를 사용하세요.  
  
 `Imports` 문을 사용하여 가져온 XML 네임스페이스에 대한 접두사는 XML 리터럴의 외부에서 사용할 수 없습니다.  
  
 **오류 ID:** BC30114  
  
### 이 오류를 해결하려면  
  
-   가져온 XML 네임스페이스의 일부를 참조해야 하는 경우 `GetXmlNamespace` 연산자를 사용하여 <xref:System.Xml.Linq.XNamespace> 개체를 검색합니다. XML 네임스페이스 접두사 대신 해당 개체를 사용합니다.  
  
-   XML 네임스페이스 접두사를 사용하여 XML 리터럴을 한정하는 경우 XML 리터럴에 대해 적절한 구문을 사용해야 합니다.  
  
## 참고 항목  
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [Imports Statement \(XML Namespace\)](/dotnet/visual-basic/language-reference/statements/imports-statement-xml-namespace)   
 [GetXmlNamespace Operator](/dotnet/visual-basic/language-reference/operators/getxmlnamespace-operator)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)