---
title: "&#39;WebMethod&#39; 특성은 포함하는 클래스가 웹 서비스로 노출되지 않으므로 이 멤버에 영향을 주지 않습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30771"
  - "bc30771"
helpviewer_keywords: 
  - "BC30771"
ms.assetid: 20b09f6a-b61a-4d89-9ca5-4632b5e68e65
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;WebMethod&#39; 특성은 포함하는 클래스가 웹 서비스로 노출되지 않으므로 이 멤버에 영향을 주지 않습니다.
<xref:System.Web.Services.WebMethodAttribute> 특성은 메서드를 원격 웹 클라이언트에서 호출할 수 있도록 만들지만 메서드의 클래스가 <xref:System.Web.Services.WebService>에서 파생될 때만 그렇습니다.  
  
 **오류 ID:** BC30771  
  
### 이 오류를 해결하려면  
  
-   <xref:System.Web.Services.WebService>에서 파생되도록 클래스를 변경합니다.  
  
     — 또는 —  
  
-   메서드에서 <xref:System.Web.Services.WebMethodAttribute> 특성을 제거합니다.  
  
## 참고 항목  
 [NIB: 연습: Visual Basic 또는 Visual C\#을 사용하여 웹 서비스 만들기](http://msdn.microsoft.com/ko-kr/295f4c3f-9540-4bd1-b1cc-3e9cb9675cc7)