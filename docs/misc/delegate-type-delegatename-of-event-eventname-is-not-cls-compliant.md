---
title: "&#39;&lt;eventname&gt;&#39; 이벤트의 &#39;&lt;delegatename&gt;&#39; 대리자 형식이 CLS 규격이 아닙니다. | Microsoft Docs"
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
  - "bc40050"
  - "vbc40050"
helpviewer_keywords: 
  - "BC40050"
ms.assetid: 92f5be26-9a82-46d4-bf97-005f2c7ca424
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;eventname&gt;&#39; 이벤트의 &#39;&lt;delegatename&gt;&#39; 대리자 형식이 CLS 규격이 아닙니다.
[Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)이 대리자를 사용하여 해당 서명을 지정하지만 [Delegate Statement](/dotnet/visual-basic/language-reference/statements/delegate-statement)이 `<CLSCompliant(False)>`로 표시되거나 표시되지 않습니다.  
  
 <xref:System.CLSCompliantAttribute> 특성을 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute>를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40050  
  
### 이 오류를 해결하려면  
  
-   CLS 규격이 필요하고 대리자의 정의를 제어하는 경우 <xref:System.CLSCompliantAttribute>를 해당 선언에 적용하여 `<CLSCompliant(True)>`로 표시합니다.  
  
-   대리자의 정의를 제어할 수 없거나 규격으로 표시할 수 없는 경우 `Event` 문에서 <xref:System.CLSCompliantAttribute>를 제거하거나 `<CLSCompliant(False)>`로 표시합니다.  
  
## 참고 항목  
 [\<PAVE OVER\> CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)