---
title: "&#39;NotInheritable&#39; 클래스에 &#39;&lt;specifiername&gt;&#39;으로 선언된 멤버를 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc30607"
  - "bc30607"
helpviewer_keywords: 
  - "BC30607"
ms.assetid: c800e24e-d055-402f-b378-6d2f4041ff16
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;NotInheritable&#39; 클래스에 &#39;&lt;specifiername&gt;&#39;으로 선언된 멤버를 사용할 수 없습니다.
재정의 한정자는 해당 멤버를 재정의할 수 없기 때문에 `NotInheritable` 클래스와 함께 사용할 수 없습니다.  
  
 **오류 ID:** BC30607  
  
### 이 오류를 해결하려면  
  
-   `Overridable`, `NotOverridable` 또는 `MustOverride`와 같은 재정의 한정자를 클래스 정의에서 제거합니다.  
  
## 참고 항목  
 [Overridable](/dotnet/visual-basic/language-reference/modifiers/overridable)   
 [NotOverridable](/dotnet/visual-basic/language-reference/modifiers/notoverridable)   
 [MustOverride](/dotnet/visual-basic/language-reference/modifiers/mustoverride)   
 [빌드에 없음: 속성 및 메서드 재정의](http://msdn.microsoft.com/ko-kr/2167e8f5-1225-4b13-9ebd-02591ba90213)