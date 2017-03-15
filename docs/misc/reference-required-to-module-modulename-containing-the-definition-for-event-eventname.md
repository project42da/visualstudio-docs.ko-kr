---
title: "&#39;&lt;eventname&gt;&#39; 이벤트에 대한 정의를 포함하는 &#39;&lt;modulename&gt;&#39; 모듈에 대한 참조가 필요합니다. | Microsoft Docs"
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
  - "vbc30006"
  - "bc30006"
helpviewer_keywords: 
  - "BC30006"
ms.assetid: 7ab80acd-b47b-4920-bb15-6a3206b984e4
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;eventname&gt;&#39; 이벤트에 대한 정의를 포함하는 &#39;&lt;modulename&gt;&#39; 모듈에 대한 참조가 필요합니다.
'\<`eventname`\>' 이벤트에 대한 정의를 포함하는 '\<`modulename`\>' 모듈에 대한 참조가 필요합니다. 하나를 프로젝트에 추가합니다.  
  
 이벤트는 프로젝트에서 직접 참조되지 않은 모듈에서 정의됩니다. 이벤트가 둘 이상의 모듈에서 정의되는 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러가 참조하는 데 모호성이 없어야 합니다.  
  
 **오류 ID:** BC30006  
  
### 이 오류를 해결하려면  
  
-   프로젝트 참조에 참조되지 않은 모듈의 이름을 포함합니다.  
  
## 참고 항목  
 [NIB: 네임스페이스 및 구성 요소 참조](http://msdn.microsoft.com/ko-kr/568fa759-796b-44cd-bf5e-1cf8de6e38fd)   
 [끊어진 참조 문제 해결](../ide/troubleshooting-broken-references.md)