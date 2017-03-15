---
title: "형식 매개 변수 제약 조건이 다르기 때문에 &#39;&lt;membername&gt;&#39;이 &#39;&lt;interfacename&gt;.&lt;interfacemembername&gt;&#39;을 구현할 수 없습니다. | Microsoft Docs"
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
  - "vbc32078"
  - "BC32078"
helpviewer_keywords: 
  - "BC32078"
ms.assetid: 2c971345-edb4-491e-9202-8eb8286b66f8
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 매개 변수 제약 조건이 다르기 때문에 &#39;&lt;membername&gt;&#39;이 &#39;&lt;interfacename&gt;.&lt;interfacemembername&gt;&#39;을 구현할 수 없습니다.
제네릭 이벤트, 속성 또는 프로시저가 인터페이스에서 정의된 유사한 멤버를 구현하려고 하지만 각각의 형식 매개 변수가 서로 다른 제약 조건 목록을 가지고 있습니다.  
  
 인터페이스 멤버를 구현하려면 구현 멤버가 인터페이스 멤버의 전체 서명뿐만 아니라 각 매개 변수의 전달 메커니즘과도 일치해야 합니다.  
  
 제네릭 인터페이스 멤버를 구현하려면 구현 멤버가 추가적으로 형식 매개 변수 수 및 각 형식 매개 변수의 제약 조건 목록과 일치해야 합니다.  
  
 인터페이스 구현에 대한 자세한 정보는 [빌드에 없음: Implements 키워드 및 Implements 문](http://msdn.microsoft.com/ko-kr/b96560f7-6413-480f-a1e2-f80253bab5be)을 참조하세요.  
  
 **오류 ID:** BC32078  
  
### 이 오류를 해결하려면  
  
-   인터페이스 멤버를 구현하려면 형식 매개 변수 제약 조건을 수정하여 인터페이스 멤버의 형식 매개 변수 제약 조건과 정확히 일치시킵니다.  
  
-   형식 매개 변수 제약 조건을 있는 그대로 유지해야 하는 경우 이 선언에서 인터페이스 멤버를 구현할 수 없습니다. 선언에서 [Implements](/dotnet/visual-basic/language-reference/statements/implements-clause) 키워드를 제거합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [빌드에 없음: Visual Basic의 인터페이스 구현 예제](http://msdn.microsoft.com/ko-kr/50bf2a30-73b6-4126-a921-075fd6eec278)