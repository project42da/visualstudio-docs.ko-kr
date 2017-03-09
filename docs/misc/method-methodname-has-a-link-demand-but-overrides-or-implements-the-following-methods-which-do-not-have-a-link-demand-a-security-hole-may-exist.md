---
title: "링크 요청이 있는 &#39;&lt;methodname&gt;&#39; 메서드에서 링크 요청이 없는 다음 메서드를 재정의하거나 구현합니다. 보안 허점이 있을 수도 있습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc42200"
  - "vbc42200"
helpviewer_keywords: 
  - "BC42200"
ms.assetid: c79d672e-638c-4d87-9b93-edf12ce84a52
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 링크 요청이 있는 &#39;&lt;methodname&gt;&#39; 메서드에서 링크 요청이 없는 다음 메서드를 재정의하거나 구현합니다. 보안 허점이 있을 수도 있습니다.
보안 링크 요청 작업이 메서드에 추가되었습니다. 그러나 메서드가 링크 요청이 없는 메서드를 재정의하거나 구현합니다. 따라서 재정의되거나 구현된 메서드를 권한 없이 호출할 수 있으며, 보안 문제가 발생할 수 있습니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42200  
  
### 이 오류를 해결하려면  
  
-   재정의되거나 구현된 메서드에 링크 요청을 추가합니다.  
  
## 참고 항목  
 [링크 요청](../Topic/Link%20Demands.md)   
 [Demand와 LinkDemand 비교](http://msdn.microsoft.com/ko-kr/1ab877f2-70f4-4e0d-8116-943999dfe8f5)   
 [보안 최적화](http://msdn.microsoft.com/ko-kr/cf255069-d85d-4de3-914a-e4625215a7c0)