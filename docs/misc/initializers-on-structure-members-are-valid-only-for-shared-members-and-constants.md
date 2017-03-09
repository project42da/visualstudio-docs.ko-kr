---
title: "구조체 멤버의 이니셜라이저는 &#39;Shared&#39; 멤버 및 상수에만 사용할 수 있습니다. | Microsoft Docs"
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
  - "bc31049"
  - "vbc31049"
helpviewer_keywords: 
  - "BC31049"
ms.assetid: 8356978e-7f84-4932-be0f-dda005c9f8ca
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 구조체 멤버의 이니셜라이저는 &#39;Shared&#39; 멤버 및 상수에만 사용할 수 있습니다.
구조체 멤버 변수가 선언의 일부로 초기화되었습니다.  
  
 **오류 ID:** BC31049  
  
### 이 오류를 해결하려면  
  
-   변수 대신 상수를 사용합니다.  
  
-   구조에 매개 변수가 있는 생성자를 추가합니다. 예:  
  
    ```  
    Structure TestStruct Public t As Integer Sub New(ByVal Tval As Integer) t = Tval End Sub End Structure  
    ```  
  
## 참고 항목  
 [How to: Declare a Structure](../Topic/How%20to:%20Declare%20a%20Structure%20\(Visual%20Basic\).md)   
 [Constants and Enumerations](/dotnet/visual-basic/programming-guide/language-features/constants-enums/index)