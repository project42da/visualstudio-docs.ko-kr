---
title: "&#39;&lt;classname&gt;&#39;은 CLS 규격이 아닌 &#39;&lt;baseclassname&gt;&#39;에서 파생되므로 CLS 규격이 아닙니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40026"
  - "bc40026"
helpviewer_keywords: 
  - "BC40026"
ms.assetid: debcd5e4-75e7-4b14-a6cc-18f1009fe52c
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;classname&gt;&#39;은 CLS 규격이 아닌 &#39;&lt;baseclassname&gt;&#39;에서 파생되므로 CLS 규격이 아닙니다.
클래스 또는 인터페이스가 `<CLSCompliant(False)>`로 표시 또는 표시되지 않은 형식을 구현하거나 해당 형식에서 파생될 때 `<CLSCompliant(True)>`로 표시되었습니다.  
  
 클래스 또는 인터페이스가 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격을 준수하려면 전체 상속 계층이 규격을 준수해야 합니다. 즉, 직접이든 간접이든 상속하는 모든 형식이 규격을 준수해야 한다는 의미입니다. 마찬가지로 클래스가 하나 이상의 인터페이스를 구현하는 경우 해당 상속 계층 전체가 모두 규격을 준수해야 합니다.  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute>를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40026  
  
### 이 오류를 해결하려면  
  
-   CLS 규격이 필요하면 다른 상속 계층 구조에서 이 형식을 정의합니다.  
  
-   이 형식이 현재 상속 계층 구조 또는 구현 체계에 유지되어야 하는 경우 해당 정의에서 <xref:System.CLSCompliantAttribute>를 제거하거나 `<CLSCompliant(False)>`로 표시합니다.  
  
## 참고 항목  
 [\<PAVE OVER\> CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)