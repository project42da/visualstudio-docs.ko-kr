---
title: "CLS 규격이 아닌 &#39;MustOverride&#39; 멤버는 CLS 규격의 &lt;classname&gt;에 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc40034"
  - "vbc40034"
helpviewer_keywords: 
  - "BC40034"
ms.assetid: 4eb36b3a-1bbe-4e99-9ecb-a12b8729b128
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CLS 규격이 아닌 &#39;MustOverride&#39; 멤버는 CLS 규격의 &lt;classname&gt;에 사용할 수 없습니다.
클래스가 `<CLSCompliant(True)>`로 표시되었지만 `<CLSCompliant(False)>`로 표시되었거나 표시되지 않은 `MustOverride` 속성 또는 프로시저를 포함합니다.  
  
 클래스가 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격인 경우 해당 클래스를 사용하는 응용 프로그램은 `<CLSCompliant(True)>`로 표시된 멤버만 액세스하고 표시되지 않은 멤버는 무시합니다. 그러나 응용 프로그램이 재정의하기 위해 `MustOverride` 속성 또는 프로시저에 액세스해야 하므로 해당 속성 또는 프로시저를 무시할 수 없습니다.  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute>를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40034  
  
### 이 오류를 해결하려면  
  
-   CLS 규격이 필요하고 클래스 소스 코드를 제어할 수 있는 경우 멤버를 `<CLSCompliant(True)>`로 표시합니다.  
  
-   CLS 규격이 필요하고 클래스 소스 코드를 제어할 수 없는 경우 또는 규격이 아닌 경우 다른 클래스 내에서 이 멤버를 정의합니다.  
  
-   이 멤버를 비규격으로 유지해야 하는 경우 해당 정의에서 `MustOverride` 키워드를 제거하거나, 클래스 정의에서 <xref:System.CLSCompliantAttribute>를 제거하거나, 클래스를 `<CLSCompliant(False)>`로 표시합니다.  
  
## 참고 항목  
 [MustOverride](/dotnet/visual-basic/language-reference/modifiers/mustoverride)   
 [\<PAVE OVER\> CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)