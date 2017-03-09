---
title: "&#39;=&#39;가 필요합니다(개체 이니셜라이저). | Microsoft Docs"
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
  - "vbc30984"
  - "bc30984"
helpviewer_keywords: 
  - "BC30984"
ms.assetid: 9cae8d32-775a-414f-9e51-0469974b6aab
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;=&#39;가 필요합니다(개체 이니셜라이저).
개체 이니셜라이저 선언에서 필드 또는 속성의 초기 값을 설정하려면 등호를 사용해야 합니다. 예를 들어 다음 선언에서는 `client`의 `Name` 속성에 대한 초기 값으로 "Microsoft"를 할당합니다.  
  
```  
Dim client As New Customer { .Name = "Microsoft" }  
```  
  
 **오류 ID:** BC30984  
  
### 이 오류를 해결하려면  
  
-   앞의 예제에 표시된 위치에 등호를 추가합니다.  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [빌드에 없음: 속성 및 속성 프로시저](http://msdn.microsoft.com/ko-kr/23e2a1ec-7e9d-4109-8940-c703d981077b)   
 [빌드에 없음: 속성 프로시저 및 필드](http://msdn.microsoft.com/ko-kr/da1c05c1-87c7-40fa-b92c-e9c7e4d170f7)