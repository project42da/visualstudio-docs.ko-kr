---
title: "&#39;System.ObsoleteAttribute&#39;는 &#39;AddHandler&#39;, &#39;RemoveHandler&#39; 또는 &#39;RaiseEvent&#39; 정의에 적용할 수 없습니다. | Microsoft Docs"
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
  - "bc31142"
  - "vbc31142"
helpviewer_keywords: 
  - "BC31142"
ms.assetid: 2bddde2e-9ca0-4f72-8910-0789a6350af8
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;System.ObsoleteAttribute&#39;는 &#39;AddHandler&#39;, &#39;RemoveHandler&#39; 또는 &#39;RaiseEvent&#39; 정의에 적용할 수 없습니다.
'System.ObsoleteAttribute'는 'AddHandler', 'RemoveHandler' 또는 'RaiseEvent' 정의에 적용할 수 없습니다. 필요한 경우 이벤트에 특성을 직접 적용하세요.  
  
 사용자 지정 이벤트가 <xref:System.ObsoleteAttribute>를 해당 `AddHandler`, `RemoveHandler` 또는 `RaiseEvent` 프로시저에 적용합니다.  
  
 <xref:System.ObsoleteAttribute>가 프로그래밍 요소를 더 이상 사용하지 않는 것으로 표시하고 사용자에게 요소가 이후 버전의 제품에서 제거된다고 알립니다.  
  
 다른 부분이 더 이상 사용되지 않는 상태에서 특정 부분의 사용자 지정 이벤트를 계속 사용하는 것은 의미가 없습니다.  
  
 **오류 ID:** BC31142  
  
### 이 오류를 해결하려면  
  
-   <xref:System.ObsoleteAttribute>를 개별 프로시저 선언에서 제거하고 이를 전체 이벤트 선언에 적용합니다.  
  
## 참고 항목  
 <xref:System.ObsoleteAttribute>   
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [AddHandler Statement](/dotnet/visual-basic/language-reference/statements/addhandler-statement)   
 [RemoveHandler Statement](/dotnet/visual-basic/language-reference/statements/removehandler-statement)   
 [RaiseEvent Statement](/dotnet/visual-basic/language-reference/statements/raiseevent-statement)