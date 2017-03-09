---
title: "접두사가 있는 네임스페이스 선언에는 XML 리터럴에 빈 값을 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc31184"
  - "vbc31184"
helpviewer_keywords: 
  - "BC31184"
ms.assetid: dde656b4-df3b-4a2e-8871-4e14832ca778
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 접두사가 있는 네임스페이스 선언에는 XML 리터럴에 빈 값을 사용할 수 없습니다.
XML 리터럴의 XML 네임스페이스 선언에 네임스페이스 값이 없습니다. 예를 들어 다음 코드에서는 이 오류를 발생시킵니다.  
  
```vb#  
Dim book = <book xmlns:ns=""/>  
```  
  
 **오류 ID:** BC31184  
  
### 이 오류를 해결하려면  
  
-   XML 네임스페이스 선언에 올바른 네임스페이스를 포함하거나 XML 리터럴에서 XML 네임스페이스 선언을 제거합니다.  
  
     대신 `Imports` 문을 사용하여 빈 네임스페이스에 대한 네임스페이스 접두사를 식별할 수 있습니다. 예:  
  
    ```vb#  
    Imports <xmlns:ns="">  
    ```  
  
## 참고 항목  
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)   
 [Imports Statement \(XML Namespace\)](/dotnet/visual-basic/language-reference/statements/imports-statement-xml-namespace)