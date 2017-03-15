---
title: "&#39;&lt;propertyname&gt;&#39; 형식이 아직 설정되지 않았으므로 무명 형식 멤버 속성 &#39;&lt;propertyname&gt;&#39;은 다른 멤버 속성의 형식을 유추하는 데 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc36559"
  - "bc36559"
helpviewer_keywords: 
  - "BC36559"
ms.assetid: 58ab8d35-9d85-4aca-8b4e-f232d7e4af61
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;propertyname&gt;&#39; 형식이 아직 설정되지 않았으므로 무명 형식 멤버 속성 &#39;&lt;propertyname&gt;&#39;은 다른 멤버 속성의 형식을 유추하는 데 사용할 수 없습니다.
무명 형식 속성의 형식이 설정될 때까지 다른 속성의 형식을 설정하는 데 사용할 수 없습니다. 예를 들어 다음 선언에서 `.LastName`이 아직 초기화되지 않았으므로 `.IDName = .LastName`은 유효하지 않습니다.  
  
```  
' Not valid.   
' Dim anon1 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}   
```  
  
 **오류 ID:** BC36559  
  
### 이 오류를 해결하려면  
  
-   속성을 사용하기 전에 그 형식을 설정하여 다른 속성을 초기화합니다.  
  
    ```  
    Dim anon2 = New With {Key .LastName = "Jones", Key .IDName = .LastName}  
    ```  
  
## 참고 항목  
 [Anonymous Types](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types)   
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../Topic/How%20to:%20Infer%20Property%20Names%20and%20Types%20in%20Anonymous%20Type%20Declarations%20\(Visual%20Basic\).md)