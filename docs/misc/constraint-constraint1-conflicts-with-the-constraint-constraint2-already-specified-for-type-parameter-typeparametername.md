---
title: "제약 조건 &#39;&lt;constraint1&gt;&#39;이 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;에 이미 지정된 제약 조건 &#39;&lt;constraint2&gt;&#39;와 충돌합니다. | Microsoft Docs"
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
  - "vbc32119"
  - "bc32119"
helpviewer_keywords: 
  - "BC32119"
ms.assetid: 30e6778d-5c2b-4f2d-a136-4e66fa9fbe4d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제약 조건 &#39;&lt;constraint1&gt;&#39;이 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;에 이미 지정된 제약 조건 &#39;&lt;constraint2&gt;&#39;와 충돌합니다.
제네릭 형식이 형식 매개 변수에서 충돌하는 제약 조건으로 선언됩니다.  
  
 다음 문은 이 오류를 생성할 수 있습니다.  
  
 `Public Class testClass(Of t As {Structure, Class })`  
  
 제약 조건 `Structure` 및 `Class`로 인해 형식 매개 변수 `t`에 대한 충돌이 발생합니다. 그 이유는 해당 형식 인수가 `Structure` 제약 조건에서는 값 형식이어야 하고 `Class`에서는 참조 형식이어야 하기 때문입니다.  
  
 **오류 ID:** BC32119  
  
### 이 오류를 해결하려면  
  
-   충돌을 방지하려면 형식 매개 변수 제약 조건을 변경합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)   
 [구조체\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/263ce115-ac36-4c05-8cb7-0e0eead5c6d0)   
 [클래스\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/0777c6e6-46bc-451b-ad70-57b49d4ef4f7)   
 [Value Types and Reference Types](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)