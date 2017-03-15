---
title: "&#39;&lt;baseclassname&gt;&#39; 기본 클래스의 &#39;&lt;constructorname&gt;&#39;이 obsolete로 표시되어 있으므로 &#39;&lt;classname&gt;&#39; 클래스에서 &#39;Sub New&#39;를 선언해야 합니다. &#39;&lt;errormessage&gt;&#39; | Microsoft Docs"
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
  - "bc30918"
  - "vbc30918"
helpviewer_keywords: 
  - "BC30918"
ms.assetid: 4879254c-4b03-4416-a4a3-e9f6b5d92a1a
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;baseclassname&gt;&#39; 기본 클래스의 &#39;&lt;constructorname&gt;&#39;이 obsolete로 표시되어 있으므로 &#39;&lt;classname&gt;&#39; 클래스에서 &#39;Sub New&#39;를 선언해야 합니다. &#39;&lt;errormessage&gt;&#39;
클래스 선언은 생성자가 없으며 기본 클래스 생성자가 <xref:System.ObsoleteAttribute> 특성 및 지시문으로 표시되어 오류로 처리합니다.  
  
 파생 클래스가 생성자를 선언하지 않는 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]가 `MyBase.New()`를 호출하는 매개 변수가 없는 암시적 생성자를 생성하려고 합니다. 인수 없이 호출될 수 있는 기본 클래스에 액세스할 수 있는 생성자가 없는 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]은 암시적 생성자를 생성할 수 없습니다. 이 경우 필요한 생성자는 <xref:System.ObsoleteAttribute> 특성으로 표시되어 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]이 호출할 수 없습니다.  
  
 프로그래밍 요소에 <xref:System.ObsoleteAttribute>를 적용하여 더 이상 사용하지 않는 요소로 표시할 수 있습니다.  이렇게 하면 특성의 <xref:System.ObsoleteAttribute.IsError%2A> 속성을 `True` 또는 `False`로 설정할 수 있습니다.`True`로 설정하면 컴파일러가 요소를 사용하려는 시도를 오류로 처리합니다.`False`로 설정하거나 기본값인 `False`로 두면 컴파일러가 요소를 사용하려는 시도가 있을 경우 경고를 발생시킵니다.  
  
 **오류 ID:** BC30918  
  
### 이 오류를 해결하려면  
  
1.  따옴표 붙은 오류 메시지를 검사하고 적절한 조치를 수행합니다.  
  
2.  `Sub New`를 사용하여 파생 클래스에서 생성자를 선언합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic에서 사용되는 특성](http://msdn.microsoft.com/ko-kr/22231318-8a40-49af-9245-e0aab723563b)   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)