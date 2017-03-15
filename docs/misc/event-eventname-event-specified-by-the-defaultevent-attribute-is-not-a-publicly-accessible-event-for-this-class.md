---
title: "&#39;DefaultEvent&#39; 특성에 의해 지정된 &#39;&lt;eventname&gt;&#39; 이벤트의 이 클래스에 대한 접근성은 public이 아닙니다. | Microsoft Docs"
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
  - "vbc30770"
  - "bc30770"
helpviewer_keywords: 
  - "BC30770"
ms.assetid: 7524fba7-2a37-4bc3-b789-87d73a166575
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;DefaultEvent&#39; 특성에 의해 지정된 &#39;&lt;eventname&gt;&#39; 이벤트의 이 클래스에 대한 접근성은 public이 아닙니다.
<xref:System.ComponentModel.DefaultEventAttribute> 특성은 특성이 적용되는 클래스에서 공개적으로 액세스할 수 있는 이벤트의 이름을 지정해야 합니다.  
  
 **오류 ID:** BC30770  
  
### 이 오류를 해결하려면  
  
1.  클래스가 공개적으로 액세스할 수 있는 이벤트를 정의하는지 확인합니다.  
  
2.  클래스의 이벤트 이름이 <xref:System.ComponentModel.DefaultEventAttribute> 특성으로 지정된 이름과 일치하는지 확인합니다.  
  
## 참고 항목  
 <xref:System.ComponentModel.DefaultEventAttribute>   
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [Class Statement](/dotnet/visual-basic/language-reference/statements/class-statement)   
 [Public](/dotnet/visual-basic/language-reference/modifiers/public)