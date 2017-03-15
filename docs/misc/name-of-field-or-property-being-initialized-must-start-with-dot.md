---
title: "초기화되는 필드 또는 속성 이름은 &#39;.&#39;로 시작해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30985"
  - "bc30985"
helpviewer_keywords: 
  - "BC30985"
ms.assetid: 4cb543e1-477c-429c-82df-541ebff08543
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 초기화되는 필드 또는 속성 이름은 &#39;.&#39;로 시작해야 합니다.
개체 이니셜라이저 목록의 각 멤버 이니셜라이저는 필드 또는 속성의 이름과 해당 초기 값을 지정합니다. 필드 또는 속성의 이름 앞에는 마침표가 와야 합니다. 예를 들어 다음 선언에서는 `client`의 `Name` 속성에 대한 초기 값으로 "Microsoft"를 할당합니다.  
  
```  
Dim client As New Customer() With { .Name = "Microsoft" }  
```  
  
 **오류 ID:** BC30985  
  
### 이 오류를 해결하려면  
  
-   각 멤버 이름 앞에 마침표를 추가합니다.  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [빌드에 없음: 속성 프로시저 및 필드](http://msdn.microsoft.com/ko-kr/da1c05c1-87c7-40fa-b92c-e9c7e4d170f7)