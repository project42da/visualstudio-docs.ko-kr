---
title: "System.Diagnostics.DebuggerHiddenAttribute는 속성 정의에 적용될 때 &#39;Get&#39; 또는 &#39;Set&#39;에 영향을 주지 않음 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc40051"
  - "vbc40051"
helpviewer_keywords: 
  - "BC40051"
ms.assetid: 623d5e48-7fb2-48a9-bbbb-92914b08c01c
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# System.Diagnostics.DebuggerHiddenAttribute는 속성 정의에 적용될 때 &#39;Get&#39; 또는 &#39;Set&#39;에 영향을 주지 않음
System.Diagnostics.DebuggerHiddenAttribute는 속성 정의에 적용될 때 'Get' 또는 'Set'에 영향을 주지 않습니다. 'Get' 및 'Set' 프로시저에 특성을 적절하게 직접 적용합니다.  
  
 <xref:System.Diagnostics.DebuggerHiddenAttribute>가 속성 선언에 적용됩니다.  
  
 소스 코드는 <xref:System.Diagnostics.DebuggerHiddenAttribute>를 프로시저에 적용할 수 있습니다. 그러면 Visual Studio 디버거에게 프로시저 내에서 중지하지 않고 프로시저에서 중단점을 설정하는 것을 허용하지 않도록 신호를 보냅니다.  
  
 속성에 <xref:System.Diagnostics.DebuggerHiddenAttribute>를 적용할 수 있지만 영향은 주지 않습니다. 속성의 `Get` 또는 `Set` 프로시저에 적용하는 경우에만 원하는 효과를 얻게 됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40051  
  
### 이 오류를 해결하려면  
  
-   속성 선언에서 <xref:System.Diagnostics.DebuggerHiddenAttribute>를 제거하고 속성의 `Get` 또는 `Set` 프로시저에 적절하게 적용합니다.  
  
## 참고 항목  
 <xref:System.Diagnostics.DebuggerHiddenAttribute>   
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)   
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement)   
 [Set Statement](/dotnet/visual-basic/language-reference/statements/set-statement)