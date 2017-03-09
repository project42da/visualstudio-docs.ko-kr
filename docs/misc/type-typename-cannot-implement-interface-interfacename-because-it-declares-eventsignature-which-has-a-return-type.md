---
title: "&#39;&lt;typename&gt;&#39; 형식은 반환 형식이 있는 &#39;&lt;eventsignature&gt;&#39;를 선언하므로 &#39;&lt;interfacename&gt;&#39; 인터페이스를 구현할 수 없습니다. | Microsoft Docs"
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
  - "bc30945"
  - "vbc30945"
helpviewer_keywords: 
  - "BC30945"
ms.assetid: 4f26e71a-949d-4103-b565-35cc8e833d29
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식은 반환 형식이 있는 &#39;&lt;eventsignature&gt;&#39;를 선언하므로 &#39;&lt;interfacename&gt;&#39; 인터페이스를 구현할 수 없습니다.
클래스 또는 구조체가 값을 반환하는 이벤트를 선언하는 인터페이스를 구현하려고 합니다.  
  
 Visual Basic에서는 현재 값을 반환하는 이벤트 선언을 지원하지 않습니다.  
  
 **오류 ID:** BC30945  
  
### 이 오류를 해결하려면  
  
-   클래스 또는 구조체 정의에서 `Implements` 문을 제거하거나 다른 인터페이스를 구현합니다.  
  
## 참고 항목  
 [빌드에 없음: 이벤트 및 이벤트 처리기](http://msdn.microsoft.com/ko-kr/95074a0d-1cbc-4221-a95a-964185c7f962)   
 [Implements Statement](/dotnet/visual-basic/language-reference/statements/implements-statement)   
 [빌드에 없음: Implements 키워드 및 Implements 문](http://msdn.microsoft.com/ko-kr/b96560f7-6413-480f-a1e2-f80253bab5be)