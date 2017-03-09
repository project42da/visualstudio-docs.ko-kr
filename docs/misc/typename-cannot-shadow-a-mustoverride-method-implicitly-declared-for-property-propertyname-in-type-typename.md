---
title: "&#39;&lt;typename&gt;&#39;은 &lt;type&gt; &#39;&lt;typename&gt;&#39;의 속성 &#39;&lt;propertyname&gt;&#39;에 대해 암시적으로 선언된 &#39;MustOverride&#39; 메서드를 숨길 수 없습니다. | Microsoft Docs"
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
  - "bc31416"
  - "vbc31416"
helpviewer_keywords: 
  - "BC31416"
ms.assetid: a52aee3c-a19e-412d-bb91-ef1b79e8675f
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;은 &lt;type&gt; &#39;&lt;typename&gt;&#39;의 속성 &#39;&lt;propertyname&gt;&#39;에 대해 암시적으로 선언된 &#39;MustOverride&#39; 메서드를 숨길 수 없습니다.
지정된 메서드 이름이 기본 클래스의 속성에 의해 암시적으로 생성된 `MustOverride` 메서드와 충돌합니다. 예를 들어 `Prop1`이라는 속성을 선언한 경우 컴파일러는 암시적 프로시저 `get_Prop1` 및 `set_Prop1`을 생성합니다.  
  
 **오류 ID:** BC31416  
  
### 이 오류를 해결하려면  
  
1.  메서드에 고유한 이름을 지정합니다.  
  
2.  기본 클래스의 속성에서 `MustOverride` 한정자를 제거합니다.  
  
## 참고 항목  
 [MustOverride](/dotnet/visual-basic/language-reference/modifiers/mustoverride)   
 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)   
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)