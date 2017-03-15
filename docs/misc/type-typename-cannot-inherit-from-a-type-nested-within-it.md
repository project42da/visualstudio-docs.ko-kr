---
title: "&#39;&lt;typename&gt;&#39; 형식은 그 안에 중첩된 형식에서 상속할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30908"
  - "vbc30908"
helpviewer_keywords: 
  - "BC30908"
ms.assetid: bca164b2-a4a9-4ed4-9f71-a9a5a42f181a
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식은 그 안에 중첩된 형식에서 상속할 수 없습니다.
클래스 또는 인터페이스 정의에는  그 안에 중첩된 형식을 지정하는 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)를 포함합니다.  
  
 상속은 원형이 아닌 선형이어야 합니다. 형식은 자신에게서 상속하는 형식에서 상속할 수 없습니다.  
  
 관련된 제한 사항은 형식은 아직 정의되지 않은 형식에서 상속할 수 없다는 것입니다. 상속에는 기본 클래스의 멤버를 다시 사용할 수 있는 기능이 포함되므로 이러한 멤버가 정의되어 있어야 합니다. 따라서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서는 다음 예제와 같은 코드를 컴파일할 수 없습니다.  
  
```  
Public Class outerClass ' The following statement is INVALID because innerClass is not defined. Inherits innerClass Public Class innerClass Public Sub doSomething() End Sub End Class End Class  
```  
  
 **오류 ID:** BC30908  
  
### 이 오류를 해결하려면  
  
-   상속 형식\(중첩의 외부 형식\)이 내부 형식에서 상속해야 하는 경우 내부 형식을 외부 형식의 밖으로 이동합니다.  
  
-   내부 형식이 외부 형식 내에 중첩되어야 하는 경우 외부 형식은 내부 형식에서 상속할 수 없습니다.[Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)를 제거합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic의 상속](http://msdn.microsoft.com/ko-kr/e5e6e240-ed31-4657-820c-079b7c79313c)