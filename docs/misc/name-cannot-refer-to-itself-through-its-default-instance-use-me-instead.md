---
title: "&#39;&lt;name&gt;&#39;은 기본 인스턴스를 통해 자신을 참조할 수 없습니다. 대신 &#39;Me&#39;를 사용하세요. | Microsoft Docs"
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
  - "vbc31139"
  - "bc31139"
helpviewer_keywords: 
  - "BC31139"
ms.assetid: 459e5d5a-d526-4cd0-934e-96e4e1eb51bb
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;name&gt;&#39;은 기본 인스턴스를 통해 자신을 참조할 수 없습니다. 대신 &#39;Me&#39;를 사용하세요.
폼 내부에서 해당 폼을 기본 인스턴스로 참조하려고 했습니다. 이 경우 폼이 자신을 재귀적으로 호출할 수 있습니다.  
  
 대체로 폼의 현재 인스턴스를 참조하는 경우 기본 인스턴스 대신 `Me`를 사용해야 합니다.  
  
 **오류 ID:** BC31139  
  
### 이 오류를 해결하려면  
  
-   `Me`를 사용하여 개체를 참조합니다.  
  
## 참고 항목  
 [디버거 기본 사항](../debugger/debugger-basics.md)