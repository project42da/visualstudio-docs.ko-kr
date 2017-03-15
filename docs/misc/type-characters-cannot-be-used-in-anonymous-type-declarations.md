---
title: "형식 문자는 무명 형식 선언에 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc36560"
  - "vbc36560"
helpviewer_keywords: 
  - "BC36560"
ms.assetid: 70eee559-d6fc-409b-b835-2c84511b160e
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 문자는 무명 형식 선언에 사용할 수 없습니다.
무명 형식의 인스턴스를 선언하는 경우 속성 이름에 형식 문자를 사용할 수 없습니다. 속성의 데이터 형식은 할당된 값에서 유추됩니다. 예를 들어 다음 선언은 잘못된 것입니다.  
  
```vb#  
'' Not valid. 'Dim anon1 = New With {.ID$ = "abc"} 'Dim anon2 = New With {.ID$ = 42}  
```  
  
 **오류 ID:** BC36560  
  
### 이 오류를 해결하려면  
  
-   이니셜라이저 목록에서 형식 문자를 제거합니다. 속성에 대해 원하는 데이터 형식을 설정해야 하는 경우 할당된 값을 명시적으로 변환할 수 있습니다.  
  
    ```vb#  
    ' Valid. Dim anon1 = New With {.ID = "abc"} Dim anon2 = New With {.ID = CStr(42)}  
    ```  
  
## 참고 항목  
 [Anonymous Types](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types)   
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../Topic/How%20to:%20Infer%20Property%20Names%20and%20Types%20in%20Anonymous%20Type%20Declarations%20\(Visual%20Basic\).md)   
 [Implicit and Explicit Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions)