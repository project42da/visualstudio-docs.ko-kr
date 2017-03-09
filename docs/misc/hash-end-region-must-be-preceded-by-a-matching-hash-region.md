---
title: "&#39;#End Region&#39;은 짝이 되는 &#39;#Region&#39; 뒤에 와야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30680"
  - "bc30680"
helpviewer_keywords: 
  - "BC30680"
ms.assetid: 1ea60620-c8dc-4957-8cf4-07b25d20da3b
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;#End Region&#39;은 짝이 되는 &#39;#Region&#39; 뒤에 와야 합니다.
`#Region`을 사용하면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코드 편집기의 개요 기능을 사용할 때 확장하거나 축소할 코드 블록을 지정할 수 있습니다.`#Region` 문의 시작과 끝은 같은 코드 블록에 있어야 합니다.  
  
 **오류 ID:** BC30680  
  
### 이 오류를 해결하려면  
  
-   해당 `#End` `Region` 문 앞의 적절한 위치에 `#Region`을 삽입합니다.  
  
## 참고 항목  
 [\#Region Directive](/dotnet/visual-basic/language-reference/directives/region-directive)