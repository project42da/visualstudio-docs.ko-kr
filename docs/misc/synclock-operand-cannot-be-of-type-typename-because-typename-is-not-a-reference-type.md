---
title: "&#39;&lt;typename&gt;&#39;이 참조 형식이 아니므로 &#39;SyncLock&#39; 피연산자는 &#39;&lt;typename&gt;&#39; 형식일 수 없습니다. | Microsoft Docs"
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
  - "vbc30582"
  - "bc30582"
helpviewer_keywords: 
  - "BC30582"
ms.assetid: 953aecf2-629a-4272-94bd-abf88f785e63
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;이 참조 형식이 아니므로 &#39;SyncLock&#39; 피연산자는 &#39;&lt;typename&gt;&#39; 형식일 수 없습니다.
`SyncLock` 문을 사용하면 여러 스레드가 동시에 동일한 문을 실행하지 않도록 하여 단일 식에서 문을 동기화할 수 있습니다.`SyncLock` 문에서 식의 형식은 클래스, 모듈, 인터페이스, 배열 또는 대리자와 같은 참조 형식이어야 합니다.  
  
 **오류 ID:** BC30582  
  
### 이 오류를 해결하려면  
  
-   형식을 적절한 참조 형식으로 변경합니다.  
  
## 참고 항목  
 [SyncLock Statement](/dotnet/visual-basic/language-reference/statements/synclock-statement)   
 [빌드에 없음: Visual Basic의 다중 스레딩](http://msdn.microsoft.com/ko-kr/c731a50c-09c1-4468-9646-54c86b75d269)