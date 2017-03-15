---
title: "XML 특성은 &#39;type&#39; 형식에서 선택할 수 없습니다. | Microsoft Docs"
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
  - "bc36808"
  - "vbc36808"
helpviewer_keywords: 
  - "BC36808"
ms.assetid: 76b2605c-3d9b-4e56-ba3f-99c60c668290
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML 특성은 &#39;type&#39; 형식에서 선택할 수 없습니다.
XML 특성이 <xref:System.Xml.Linq.XElement> 또는 `IEnumerable(Of XElement)` 형식이 아닌 개체에 대해 참조되었습니다. 자세한 내용은 [XML Attribute Axis Property](/dotnet/visual-basic/language-reference/xml-axis/xml-attribute-axis-property)을 참조하세요.  
  
```vb#  
' Generates an error. Dim var = "sample text".@attr  
```  
  
 **오류 ID:** BC36808  
  
### 이 오류를 해결하려면  
  
-   특성을 참조하는 개체가 <xref:System.Xml.Linq.XElement> 또는 `IEnumerable(Of XElement)`로 강력하게 형식화되었는지 확인합니다. 예를 들면 다음과 같습니다.  
  
    ```vb#  
    Dim elem As XElement = <root attr="value"/> Dim var = elem.@attr  
    ```  
  
## 참고 항목  
 [XML Attribute Axis Property](/dotnet/visual-basic/language-reference/xml-axis/xml-attribute-axis-property)   
 [XML Axis Properties](/dotnet/visual-basic/language-reference/xml-axis/xml-axis-properties)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)