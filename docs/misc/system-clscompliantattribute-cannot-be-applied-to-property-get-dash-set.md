---
title: "System.CLSCompliantAttribute는 &#39;Get&#39;/&#39;Set&#39; 속성에 적용할 수 없습니다. | Microsoft Docs"
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
  - "vbc40043"
  - "BC40043"
helpviewer_keywords: 
  - "BC40043"
ms.assetid: 2ff45c09-32be-4ca9-b42a-63ce2536db7d
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# System.CLSCompliantAttribute는 &#39;Get&#39;/&#39;Set&#39; 속성에 적용할 수 없습니다.
속성 정의는 <xref:System.CLSCompliantAttribute> 특성을 해당 `Get` 또는 `Set` 문에 적용합니다.  
  
 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\)를 따르는 속성의 경우 전체 속성이 `<CLSCompliant(True)>`로 표시되어야 합니다.`Get` 또는 `Set` 문이 아닌 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)에 <xref:System.CLSCompliantAttribute>를 적용해야 합니다.  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute>를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40043  
  
### 이 오류를 해결하려면  
  
-   `Get` 또는 `Set` 문에서 <xref:System.CLSCompliantAttribute>를 제거합니다.  
  
-   속성이 CLS 규격을 준수해야 하면 `Property` 문을 `<CLSCompliant(True)>`로 표시합니다.  
  
## 참고 항목  
 [\<PAVE OVER\> CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)   
 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement)   
 [Set Statement](/dotnet/visual-basic/language-reference/statements/set-statement)