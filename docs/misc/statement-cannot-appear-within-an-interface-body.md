---
title: "인터페이스 본문 안에는 문을 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc30603"
  - "BC30603"
helpviewer_keywords: 
  - "BC30603"
ms.assetid: 3aef29d6-eadf-4f1f-b214-dfeae5e51c4f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 인터페이스 본문 안에는 문을 사용할 수 없습니다.
인터페이스 멤버 선언에는 멤버를 종료하는 문이 `End` *membername* 형식으로 포함됩니다.  
  
 인터페이스는 해당 멤버의 서명만 정의합니다. 따라서 인터페이스에 정의된 프로시저 및 속성에 이름과 서명을 지정하는 초기 줄만 있습니다. 코드, 내부 선언 또는 `End Function`, `End Property` 또는 `End Sub` 문은 인터페이스 내에 포함하지 않습니다.  
  
 **오류 ID:** BC30603  
  
### 이 오류를 해결하려면  
  
-   인터페이스 정의에서 `End` *membername* 문을 제거합니다.  
  
## 참고 항목  
 [Interface Statement](/dotnet/visual-basic/language-reference/statements/interface-statement)   
 [End \<keyword\> Statement](../Topic/End%20%3Ckeyword%3E%20Statement%20\(Visual%20Basic\).md)