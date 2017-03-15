---
title: "&#39;End Set&#39;은 짝이 되는 &#39;Set&#39; 뒤에 와야 합니다. | Microsoft Docs"
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
  - "bc30632"
  - "vbc30632"
helpviewer_keywords: 
  - "BC30632"
ms.assetid: 0c3dd065-566b-485c-9996-6177eb0fde39
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;End Set&#39;은 짝이 되는 &#39;Set&#39; 뒤에 와야 합니다.
`End Set`은 `Set` 속성 프로시저를 종료하는 데 사용됩니다.`Set` 속성 프로시저 외부에서 `End Set` 구문이 발생했습니다.  
  
 **오류 ID:** BC30632  
  
### 이 오류를 해결하려면  
  
1.  `Set` 속성 프로시저가 `Property` 키워드 뒤와 `End Property` 구문 앞에서 선언되었는지 확인합니다.  
  
2.  `Set` 속성 프로시저가 `Set` 키워드로 시작하고 `End Set` 구문으로 끝나는지 확인합니다.  
  
## 참고 항목  
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Property Changes in Visual Basic](http://msdn.microsoft.com/ko-kr/1c138efa-9bc2-44d7-80a0-f3a7c2510264)