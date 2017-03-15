---
title: "마침표가 앞에 오는 식별자가 필요합니다. | Microsoft Docs"
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
  - "bc36576"
  - "vbc36576"
helpviewer_keywords: 
  - "BC36576"
ms.assetid: 02217cc4-8972-4a6d-97a6-4ecbb7399af2
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 마침표가 앞에 오는 식별자가 필요합니다.
속성 이름을 유추할 수 없는 값이 속성 이름에 할당되지 않고 무명 형식 선언의 이니셜라이저 목록에 포함되었습니다.  
  
```  
' Not valid. ' Dim anon1 = New With {.grade = 100, 95}  
```  
  
 **오류 ID:** BC36576  
  
### 이 오류를 해결하려면  
  
-   다음 코드와 같이 이니셜라이저 목록의 각 값에 대해 속성 이름을 지정합니다.  
  
    ```  
    Dim anon2 = New With {.grade1 = 100, .grade2 = 95}  
    ```  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [방법: 무명 형식의 인스턴스 선언\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/119f616c-9bcd-4731-ac00-4285be5959f7)   
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../Topic/How%20to:%20Infer%20Property%20Names%20and%20Types%20in%20Anonymous%20Type%20Declarations%20\(Visual%20Basic\).md)