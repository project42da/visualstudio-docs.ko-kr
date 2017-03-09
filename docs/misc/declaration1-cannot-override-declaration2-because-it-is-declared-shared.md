---
title: "&#39;&lt;declaration1&gt;&#39;은 &#39;Shared&#39;로 선언되므로 &#39;&lt;declaration2&gt;&#39;를 재정의할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30268"
  - "bc30268"
helpviewer_keywords: 
  - "BC30268"
ms.assetid: d011fb26-6236-462e-9173-622f8bbeb536
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;declaration1&gt;&#39;은 &#39;Shared&#39;로 선언되므로 &#39;&lt;declaration2&gt;&#39;를 재정의할 수 없습니다.
프로시저나 속성 선언이 동일한 이름의 상속된 요소를 재정의하려고 하지만 상속된 요소가 `Shared`로 지정되었습니다. 공유 요소는 클래스 인스턴스와 연결되어 있지 않으므로 재정의할 수 없습니다.  
  
 **오류 ID:** BC30268  
  
### 이 오류를 해결하려면  
  
-   상속된 요소에서 `Shared` 키워드를 제거하거나 재정의 선언을 제거합니다.  
  
## 참고 항목  
 [빌드에 없음: 속성 및 메서드 재정의](http://msdn.microsoft.com/ko-kr/2167e8f5-1225-4b13-9ebd-02591ba90213)