---
title: "&#39;{&#39;가 필요합니다. | Microsoft Docs"
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
  - "vbc30987"
  - "bc30987"
helpviewer_keywords: 
  - "BC30987"
ms.assetid: 3d1552b6-338a-47cf-84d5-77b59209e0d3
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;{&#39;가 필요합니다.
개체 이니셜라이저를 사용하여 명명된 형식이나 무명 형식의 인스턴스를 선언하려면 필드 또는 속성과 해당 초기값의 목록을 중괄호\({ 및 }\)로 묶어야 합니다.  
  
```  
Dim client As New Customer() With {.Name = "Microsoft", .City = "Seattle"}  
Dim emp = New Employee() With {.Name = "Rob Young", .ID = 55555}  
Dim anon = New With {.ID = 123456}  
```  
  
 **오류 ID:** BC30987  
  
### 이 오류를 해결하려면  
  
-   초기화 목록을 중괄호로 묶어서 `With` 뒤에 포함합니다.  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [빌드에 없음: 속성 프로시저 및 필드](http://msdn.microsoft.com/ko-kr/da1c05c1-87c7-40fa-b92c-e9c7e4d170f7)   
 [Anonymous Types](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types)