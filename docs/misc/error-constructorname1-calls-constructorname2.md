---
title: "&lt;error&gt;: &#39;&lt;constructorname1&gt;&#39;이 &#39;&lt;constructorname2&gt;&#39;를 호출합니다. | Microsoft Docs"
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
  - "vbc30297"
  - "bc30297"
helpviewer_keywords: 
  - "BC30297"
ms.assetid: dfca67d7-f4d7-4451-a937-68f22b8527d5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;error&gt;: &#39;&lt;constructorname1&gt;&#39;이 &#39;&lt;constructorname2&gt;&#39;를 호출합니다.
순환 생성자 호출이 발생합니다. 생성자가 `Me.New()` 또는 `MyClass.New()`를 호출합니다. 서로 다른 인수 목록을 사용하는 오버로드된 생성자를 호출하려는 시도 때문일 수 있습니다.  
  
 **오류 ID:** BC30297  
  
### 이 오류를 해결하려면  
  
-   서로 다른 인수 목록이 사용하여 오버로드된 생성자를 호출합니다.  
  
-   액세스할 수 있는 오버로드가 없는 경우 `Me.New()` 또는 `MyClass.New()`에 대한 호출을 제거합니다.  
  
## 참고 항목  
 [빌드에 없음: 생성자 및 소멸자 사용](http://msdn.microsoft.com/ko-kr/548eebe1-86c4-4377-b2f5-447cb8be3d90)