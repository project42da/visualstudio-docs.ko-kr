---
title: "&#39;Exit Do&#39;는 &#39;Do&#39; 문 내부에만 사용할 수 있습니다. | Microsoft Docs"
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
  - "bc30089"
  - "vbc30089"
helpviewer_keywords: 
  - "BC30089"
ms.assetid: 0e1d0b35-e42b-4b90-b8a2-91fd6ef44f06
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Exit Do&#39;는 &#39;Do&#39; 문 내부에만 사용할 수 있습니다.
`Exit Do` 문이 `Do` 루프 외부에서 발생합니다.`Exit Do`는 `Do` 문과 해당 `Loop` 문 사이에만 사용할 수 있습니다.  
  
 **오류 ID:** BC30089  
  
### 이 오류를 해결하려면  
  
1.  유효한 `Do` 문이 `Exit Do` 앞에 있고 유효한 `Loop` 문이 그 뒤에 있는지 확인합니다.  
  
2.  `Do` 루프 내의 다른 컨트롤 구조가 올바르게 종료되었는지 확인합니다.  
  
## 참고 항목  
 [Do...Loop Statement](/dotnet/visual-basic/language-reference/statements/do-loop-statement)