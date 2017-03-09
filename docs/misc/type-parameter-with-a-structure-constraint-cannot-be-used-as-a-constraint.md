---
title: "&#39;Structure&#39; 제약 조건이 있는 형식 매개 변수는 제약 조건으로 사용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32114"
  - "bc32114"
helpviewer_keywords: 
  - "BC32114"
ms.assetid: 442b2048-9dc4-4223-bcfc-4d96bf8d14de
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Structure&#39; 제약 조건이 있는 형식 매개 변수는 제약 조건으로 사용할 수 없습니다.
`Structure` 제약 조건이 있는 형식 매개 변수가 다른 형식 매개 변수에 대한 제약 조건으로 사용되었습니다.  
  
 `Structure` 제약 조건에서는 해당 형식 매개 변수에 전달된 형식 인수가 값 형식이어야 합니다. 그러나 값 형식을 구현하거나 상속할 수 없으므로 제약 조건으로 사용해도 의미가 없으며, 다른 형식 매개 변수가 구현하거나 상속해야 합니다.  
  
 이러한 상황의 의미 있는 해석은 두 형식 인수가 정확히 동일한 형식이어야 한다는 것뿐입니다. 해당되는 경우 제네릭 형식에는 하나의 형식 매개 변수만 필요합니다.  
  
 다음 문은 이 오류를 생성할 수 있습니다.  
  
 `Class c1(Of t1 As Structure, t2 As t1)`  
  
 `t1`에 전달된 형식은 값 형식이어야 하므로 `t2`에 전달된 형식이 `t1`에 전달된 형식을 구현하거나 상속할 수 없습니다.  
  
 **오류 ID:** BC32114  
  
### 이 오류를 해결하려면  
  
-   다른 형식 매개 변수의 제약 조건 목록에서 `Structure`로 제한된 형식 매개 변수를 제거합니다.  
  
-   두 형식 매개 변수에 모두 동일한 값 형식이 필요한 경우 하나의 형식 매개 변수만 사용하여 제네릭 형식을 정의합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)   
 [구조체\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/263ce115-ac36-4c05-8cb7-0e0eead5c6d0)   
 [Value Types and Reference Types](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)