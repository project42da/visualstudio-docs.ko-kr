---
title: "&#39;&lt;classname&gt;&#39; 클래스를 &#39;MustInherit&#39;으로 선언하거나, 상속된 &#39;MustOverride&#39; 멤버인 &lt;membername(s)&gt;을 재정의해야 합니다. | Microsoft Docs"
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
  - "bc30610"
  - "vbc30610"
helpviewer_keywords: 
  - "BC30610"
ms.assetid: 7fba7a3b-c918-44ba-ae85-20312615c1ce
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;classname&gt;&#39; 클래스를 &#39;MustInherit&#39;으로 선언하거나, 상속된 &#39;MustOverride&#39; 멤버인 &lt;membername(s)&gt;을 재정의해야 합니다.
`MustOverride` 멤버를 포함하는 기본 클래스에서 파생된 클래스는 이러한 멤버를 재정의하거나 `MustInherit` 한정자를 사용해야 합니다.  
  
 **오류 ID:** BC30610  
  
### 이 오류를 해결하려면  
  
-   클래스 정의에 `MustInherit` 한정자를 추가합니다.  
  
-   `Overrides` 키워드를 사용하여 재정의를 선언합니다.  
  
## 참고 항목  
 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides)   
 [MustInherit](/dotnet/visual-basic/language-reference/modifiers/mustinherit)   
 [빌드에 없음: Visual Basic의 상속](http://msdn.microsoft.com/ko-kr/e5e6e240-ed31-4657-820c-079b7c79313c)