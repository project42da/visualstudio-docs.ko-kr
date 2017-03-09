---
title: "형식 또는 &#39;With&#39;가 필요합니다. | Microsoft Docs"
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
  - "vbc30988"
  - "bc30988"
helpviewer_keywords: 
  - "BC30988"
ms.assetid: ab9c0cee-9fe4-4764-a3c2-aec16e709d4c
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 또는 &#39;With&#39;가 필요합니다.
클래스의 인스턴스를 선언하는 경우 `New` 키워드 다음에 형식 이름 또는 `With`가 나와야 합니다. 예를 들어 다음 문은 각각 `Customer` 클래스의 인스턴스가 될 `client`을 선언합니다. 형식 이름 `Customer`가 `New` 뒤에 나옵니다.  
  
```  
' Dim client As New Customer()  
' The next declaration uses an object initializer.  
Dim client As New Customer() With {.Name = "Litware, Inc."}  
```  
  
 [!INCLUDE[vb_orcas_long](../misc/includes/vb_orcas_long_md.md)]에서 시작하여 무명 형식의 인스턴스가 될 개체를 선언할 수 있으며, 이 경우 데이터 형식을 지정하지 않습니다. 무명 형식 선언에서 `With` 키워드는 `New` 뒤에 나옵니다.  
  
```  
Dim person = New With {.Name ="Mike Nash", .Age = 27}  
```  
  
 **오류 ID:** BC30988  
  
### 이 오류를 해결하려면  
  
-   `With` 또는 형식 이름이 `New` 뒤에 나오도록 선언을 변경합니다.  
  
## 참고 항목  
 [Anonymous Types](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types)   
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator)   
 [NotInBuild:Visual Basic의 선언문](http://msdn.microsoft.com/ko-kr/81f3c398-f45c-4d95-80bf-aa39d1a0fb30)