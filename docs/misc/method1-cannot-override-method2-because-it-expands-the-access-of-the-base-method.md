---
title: "&#39;&lt;method1&gt;&#39;이 기본 메서드의 액세스를 확장하기 때문에 &#39;&lt;method2&gt;&#39;를 재정의할 수 없습니다. | Microsoft Docs"
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
  - "vbc32203"
  - "bc32203"
helpviewer_keywords: 
  - "BC32203"
ms.assetid: ef7816a4-5f57-4346-80fc-9311bc150b6b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;method1&gt;&#39;이 기본 메서드의 액세스를 확장하기 때문에 &#39;&lt;method2&gt;&#39;를 재정의할 수 없습니다.
프로시저가 `Overrides`를 지정하지만 재정의될 메서드의 접근성보다 덜 제한적인 접근성을 선언합니다. 접근성을 확장할 수 없습니다. 즉 재정의하는 메서드를 재정의되는 메서드보다 더 액세스 가능하도록 만들 수 없습니다. 예를 들어 기본 클래스 메서드가 `Protected`이면 이 메서드를 `Public` 메서드로 재정의할 수 없습니다.  
  
 **오류 ID:** BC32203  
  
### 이 오류를 해결하려면  
  
-   `Overrides` 키워드를 제거하거나 접근성이 기본 클래스 메서드 이상으로 제한적이 되도록 변경합니다.  
  
## 참고 항목  
 [빌드에 없음: 속성 및 메서드 재정의](http://msdn.microsoft.com/ko-kr/2167e8f5-1225-4b13-9ebd-02591ba90213)   
 [Access Levels in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/access-levels)   
 [Shadowing in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/shadowing)