---
title: "&#39;&lt;propertyname&gt;&#39;의 &#39;&lt;keyword&gt;&#39; 접근자는 사용되지 않습니다. &#39;&lt;errormessage&gt;&#39;(Visual Basic 경고) | Microsoft Docs"
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
  - "bc40019"
  - "vbc40019"
helpviewer_keywords: 
  - "BC40019"
ms.assetid: 57d00655-1837-4605-a5e9-1ae5b6935f51
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;propertyname&gt;&#39;의 &#39;&lt;keyword&gt;&#39; 접근자는 사용되지 않습니다. &#39;&lt;errormessage&gt;&#39;(Visual Basic 경고)
문에서 해당 프로시저를 <xref:System.ObsoleteAttribute> 특성 및 지시문으로 표시하여 경고로 처리하는 속성을 읽거나 쓰려고 합니다.  
  
 프로그래밍 요소에 <xref:System.ObsoleteAttribute>를 적용하여 더 이상 사용하지 않는 요소로 표시할 수 있습니다.  이렇게 하면 특성의 <xref:System.ObsoleteAttribute.IsError%2A> 속성을 `True` 또는 `False`로 설정할 수 있습니다.`True`로 설정하면 컴파일러가 요소를 사용하려는 시도를 오류로 처리합니다.`False`로 설정하거나 기본값인 `False`로 두면 컴파일러가 요소를 사용하려는 시도가 있을 경우 경고를 발생시킵니다.  
  
 <xref:System.ObsoleteAttribute>의 <xref:System.ObsoleteAttribute.IsError%2A> 속성이 `False`이므로 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40019  
  
### 이 오류를 해결하려면  
  
1.  따옴표 붙은 오류 메시지를 검사하고 적절한 조치를 수행합니다.  
  
2.  소스 코드 참조에서 속성 이름의 철자가 올바른지 확인합니다.  
  
3.  이 메시지를 생성한 방법\(읽기 또는 쓰기\)으로 해당 속성에 액세스하지 않아야 합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic에서 사용되는 특성](http://msdn.microsoft.com/ko-kr/22231318-8a40-49af-9245-e0aab723563b)   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)