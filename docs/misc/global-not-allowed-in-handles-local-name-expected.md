---
title: "핸들에는 &#39;Global&#39;을 사용할 수 없습니다. 로컬 이름이 필요합니다. | Microsoft Docs"
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
  - "bc36002"
  - "vbc36002"
helpviewer_keywords: 
  - "BC36002"
ms.assetid: 7b4602a9-84c9-4068-81bc-e8df03ffc130
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 핸들에는 &#39;Global&#39;을 사용할 수 없습니다. 로컬 이름이 필요합니다.
`Handles` 절은 로컬 이벤트를 참조해야 합니다.`Global` 키워드는 전역 프로그래밍 요소에 대한 액세스를 제공합니다.  
  
 **오류 ID:** BC36002  
  
### 이 오류를 해결하려면  
  
-   전역 인스턴스 대신 이벤트의 로컬 인스턴스를 참조하도록 `Handles` 절을 변경합니다.  
  
## 참고 항목  
 [Global \- 삭제](http://msdn.microsoft.com/ko-kr/18c8ba14-40f6-4978-8096-6a5852324635)   
 [Handles](/dotnet/visual-basic/language-reference/statements/handles-clause)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)