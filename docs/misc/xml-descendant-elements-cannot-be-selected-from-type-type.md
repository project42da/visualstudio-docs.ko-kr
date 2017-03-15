---
title: "XML 하위 요소는 &#39;type&#39; 형식에서 선택할 수 없습니다. | Microsoft Docs"
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
  - "vbc36809"
  - "bc36809"
helpviewer_keywords: 
  - "BC36809"
ms.assetid: 560a3370-f24d-4ca3-93b1-39aabe13c238
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML 하위 요소는 &#39;type&#39; 형식에서 선택할 수 없습니다.
XML 하위 항목이 <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> 또는 `IEnumerable(Of XElement)` 형식이 아닌 개체에 대해 참조되었습니다. 자세한 내용은 [XML Descendant Axis Property](/dotnet/visual-basic/language-reference/xml-axis/xml-descendant-axis-property)을 참조하세요.  
  
```vb#  
' Generates an error. Dim var = "sample text"...<childElement>  
```  
  
 **오류 ID:** BC36809  
  
### 이 오류를 해결하려면  
  
-   하위 요소를 참조하는 개체가 <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> 또는 `IEnumerable(Of XElement)`로 강력하게 형식화되었는지 확인합니다. 예를 들면 다음과 같습니다.  
  
    ```vb#  
    Dim elem As XElement = <root> <child /> </root> Dim var = elem...<child>  
    ```  
  
## 참고 항목  
 [XML Descendant Axis Property](/dotnet/visual-basic/language-reference/xml-axis/xml-descendant-axis-property)   
 [XML Axis Properties](/dotnet/visual-basic/language-reference/xml-axis/xml-axis-properties)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)