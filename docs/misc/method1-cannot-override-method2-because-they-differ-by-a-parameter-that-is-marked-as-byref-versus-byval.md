---
title: "&#39;ByRef&#39; 또는 &#39;ByVal&#39;로 표시된 매개 변수가 서로 다르므로 &#39;&lt;method1&gt;&#39;은 &#39;&lt;method2&gt;&#39;를 재정의할 수 없습니다. | Microsoft Docs"
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
  - "vbc30398"
  - "bc30398"
helpviewer_keywords: 
  - "BC30398"
ms.assetid: 78d62276-4ad9-4876-8c35-a30c9c195638
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ByRef&#39; 또는 &#39;ByVal&#39;로 표시된 매개 변수가 서로 다르므로 &#39;&lt;method1&gt;&#39;은 &#39;&lt;method2&gt;&#39;를 재정의할 수 없습니다.
매개 변수가 `ByVal` 대신 `ByRef`로 표시된 메서드로 메서드를 재정의하려고 했습니다. 재정의된 멤버에 기본 클래스에서 상속된 멤버와 동일한 인수가 있어야 합니다.  
  
 **오류 ID:** BC30398  
  
### 이 오류를 해결하려면  
  
-   매개 변수가 둘 다 `ByRef`이거나 둘 다 `ByVal`인지 확인합니다.  
  
## 참고 항목  
 [빌드에 없음: 속성 및 메서드 재정의](http://msdn.microsoft.com/ko-kr/2167e8f5-1225-4b13-9ebd-02591ba90213)   
 [Passing Arguments by Value and by Reference](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference)