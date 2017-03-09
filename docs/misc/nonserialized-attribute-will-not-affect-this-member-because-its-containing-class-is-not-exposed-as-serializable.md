---
title: "&#39;NonSerialized&#39; 특성은 포함하는 클래스가 &#39;Serializable&#39;로 노출되지 않으므로 이 멤버에 영향을 주지 않습니다. | Microsoft Docs"
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
  - "vbc30772"
  - "bc30772"
helpviewer_keywords: 
  - "BC30772"
ms.assetid: 1014e944-40c1-4078-8a38-139736ef89da
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;NonSerialized&#39; 특성은 포함하는 클래스가 &#39;Serializable&#39;로 노출되지 않으므로 이 멤버에 영향을 주지 않습니다.
기본적으로 클래스와 해당 멤버는 직렬화할 수 없습니다.<xref:System.NonSerializedAttribute> 특성은 serializable 클래스의 멤버를 직렬화하지 않아야 하는 경우에만 필요합니다.  
  
 **오류 ID:** BC30772  
  
### 이 오류를 해결하려면  
  
-   클래스에 <xref:System.SerializableAttribute> 특성을 추가합니다.  
  
     또는  
  
-   멤버에서 <xref:System.NonSerializedAttribute> 특성을 제거합니다.  
  
## 참고 항목  
 <xref:System.NonSerializedAttribute>   
 <xref:System.SerializableAttribute>   
 [빌드에 없음: Visual Basic의 특성](http://msdn.microsoft.com/ko-kr/620bfc0e-4582-4c8b-8432-ebc5c3dccc22)