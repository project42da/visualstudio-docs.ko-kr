---
title: "&#39;#Region&#39; 문은 짝이 맞는 &#39;#End Region&#39;으로 끝나야 합니다. | Microsoft Docs"
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
  - "bc30681"
  - "vbc30681"
helpviewer_keywords: 
  - "BC30681"
ms.assetid: 05a0402b-da68-4ab8-b6d6-940379bc5973
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;#Region&#39; 문은 짝이 맞는 &#39;#End Region&#39;으로 끝나야 합니다.
`#Region` 지시문을 사용하면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코드 편집기의 개요 기능을 사용할 때 확장하거나 축소할 수 있는 코드 블록을 지정할 수 있습니다.`#Region` 문의 시작과 끝은 같은 코드 블록에 있어야 합니다.  
  
 **오류 ID:** BC30681  
  
### 이 오류를 해결하려면  
  
1.  코드에서 `#Region` 문 뒤의 적절한 위치에 `#End Region`을 삽입합니다.  
  
## 참고 항목  
 [\#Region Directive](/dotnet/visual-basic/language-reference/directives/region-directive)