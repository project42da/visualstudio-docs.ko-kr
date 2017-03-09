---
title: "네임스페이스 선언은 &#39;xmlns&#39;로 시작해야 합니다. | Microsoft Docs"
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
  - "bc31187"
  - "vbc31187"
helpviewer_keywords: 
  - "BC31187"
ms.assetid: 64c6a033-7cdc-48a0-bff0-bdd045cb13ad
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 네임스페이스 선언은 &#39;xmlns&#39;로 시작해야 합니다.
XML 네임스페이스를 필요한 `xmlns` 식별자 없이 지정했습니다.`xmlns` 식별자에는 소문자만 포함되어야 합니다.  
  
 **오류 ID:** BC31187  
  
### 이 오류를 해결하려면  
  
-   XML 네임스페이스를 선언할 때 `xmlns` 식별자를 사용합니다. 예를 들면 다음과 같습니다.  
  
    ```vb#  
    Imports <xmlns:ns="http://SampleNamespace">  
    ```  
  
## 참고 항목  
 [Imports Statement \(XML Namespace\)](/dotnet/visual-basic/language-reference/statements/imports-statement-xml-namespace)   
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)