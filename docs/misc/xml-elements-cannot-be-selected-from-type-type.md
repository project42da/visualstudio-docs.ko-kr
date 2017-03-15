---
title: "XML 요소는 &#39;type&#39; 형식에서 선택할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36807"
  - "bc36807"
helpviewer_keywords: 
  - "BC36807"
ms.assetid: 01c19899-2b44-41e9-a99c-35edfa0deaf1
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML 요소는 &#39;type&#39; 형식에서 선택할 수 없습니다.
XML 자식 요소가 <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> 또는 `IEnumerable(Of XElement)` 형식이 아닌 개체에 대해 참조되었습니다. 자세한 내용은 [XML Child Axis Property](/dotnet/visual-basic/language-reference/xml-axis/xml-child-axis-property)을 참조하세요.  
  
```vb#  
' Generates an error. Dim var = "sample text".<child>  
```  
  
 **오류 ID:** BC36807  
  
### 이 오류를 해결하려면  
  
-   특성을 참조하는 개체가 <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> 또는 `IEnumerable(Of XElement)`로 강력하게 형식화되었는지 확인합니다. 예를 들면 다음과 같습니다.  
  
    ```vb#  
    Dim elem As XElement = <root> <child /> </root> Dim var = elem.<child>  
    ```  
  
## 참고 항목  
 [XML Child Axis Property](/dotnet/visual-basic/language-reference/xml-axis/xml-child-axis-property)   
 [XML Axis Properties](/dotnet/visual-basic/language-reference/xml-axis/xml-axis-properties)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)