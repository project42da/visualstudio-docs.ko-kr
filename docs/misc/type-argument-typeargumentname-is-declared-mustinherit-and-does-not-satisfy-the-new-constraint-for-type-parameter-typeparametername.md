---
title: "형식 인수 &#39;&lt;typeargumentname&gt;&#39;은 &#39;MustInherit&#39;으로 선언되었으며 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;에 대한 &#39;New&#39; 제약 조건을 만족하지 않습니다. | Microsoft Docs"
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
  - "vbc32082"
  - "BC32082"
helpviewer_keywords: 
  - "BC32082"
ms.assetid: 597e5944-a61b-4858-ada5-efb80b27f26b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 인수 &#39;&lt;typeargumentname&gt;&#39;은 &#39;MustInherit&#39;으로 선언되었으며 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;에 대한 &#39;New&#39; 제약 조건을 만족하지 않습니다.
제네릭 형식이 형식 인수로 `MustInherit` 클래스를 사용하여 호출되었는데 해당 형식 매개 변수가 `New` 제약 조건을 사용하여 선언되었습니다.  
  
 `New` 제약 조건에서는 해당 형식 인수에 전달된 형식이 개체 생성을 지원해야 합니다. 그러나 *abstract* 클래스, 즉 `MustInherit`로 선언된 클래스가 개체를 생성할 수 없기 때문에 생성자를 노출하지 않습니다.  
  
 **오류 ID:** BC32082  
  
### 이 오류를 해결하려면  
  
1.  형식 인수에 사용된 클래스가 추상일 필요가 없는 경우 해당 선언에서 `MustInherit` 키워드를 제거합니다.  
  
2.  형식 인수에 사용된 클래스가 추상이어야 하지만 제네릭 형식을 구성하는 데 사용할 필요가 없는 경우 형식 인수에서 다른 클래스를 전달합니다.  
  
3.  해당 형식 매개 변수가 전달된 형식에서 아무 개체를 만들 필요가 없는 경우 해당 선언에서 `New` 제약 조건을 제거합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator)   
 [MustInherit](/dotnet/visual-basic/language-reference/modifiers/mustinherit)