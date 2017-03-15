---
title: "액세스 수준이 서로 달라 &#39;&lt;declaration1&gt;&#39;에서는 &#39;&lt;declaration2&gt;&#39;를 재정의할 수 없습니다. | Microsoft Docs"
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
  - "bc30266"
  - "vbc30266"
helpviewer_keywords: 
  - "BC30266"
ms.assetid: c9c5c14e-876c-430d-ab98-5087c19efae7
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 액세스 수준이 서로 달라 &#39;&lt;declaration1&gt;&#39;에서는 &#39;&lt;declaration2&gt;&#39;를 재정의할 수 없습니다.
프로시저나 속성 선언이 동일한 이름의 상속된 요소를 재정의하려고 하지만 상속된 요소와 다른 접근성을 지정합니다. 재정의할 때 `Public` 또는 `Private`와 같은 상속된 요소의 접근성을 유지해야 합니다.  
  
 **오류 ID:** BC30266  
  
### 이 오류를 해결하려면  
  
-   재정의하는 요소의 접근성을 상속된 요소의 접근성과 일치하도록 변경합니다.  
  
## 참고 항목  
 [빌드에 없음: 속성 및 메서드 재정의](http://msdn.microsoft.com/ko-kr/2167e8f5-1225-4b13-9ebd-02591ba90213)   
 [Access Levels in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/access-levels)