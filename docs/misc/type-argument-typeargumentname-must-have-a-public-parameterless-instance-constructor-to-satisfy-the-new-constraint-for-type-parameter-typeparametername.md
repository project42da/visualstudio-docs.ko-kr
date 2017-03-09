---
title: "형식 매개 변수 &#39;&lt;typeargumentname&gt;&#39;에 대한 &#39;New&#39; 제약 조건을 만족하려면 형식 인수 &#39;&lt;typeparametername&gt;&#39;에 매개 변수가 없는 public 인스턴스 생성자가 있어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32083"
  - "BC32083"
helpviewer_keywords: 
  - "BC32083"
ms.assetid: 56bf25f1-375c-4b5d-9969-45eba8b3b66c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 매개 변수 &#39;&lt;typeargumentname&gt;&#39;에 대한 &#39;New&#39; 제약 조건을 만족하려면 형식 인수 &#39;&lt;typeparametername&gt;&#39;에 매개 변수가 없는 public 인스턴스 생성자가 있어야 합니다.
형식 인수에서 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator) 제약 조건이 있는 형식 매개 변수에 대해 액세스 가능하고 매개 변수가 없는 생성자 없이 형식을 제공합니다.  
  
 제약 조건 목록은 형식 매개 변수에 전달되는 형식 인수에 대해 요구 사항을 적용합니다. 이러한 요구 사항 중 하나는 해당 형식 인수에서 만드는 코드에 액세스할 수 있는, 매개 변수 없는 생성자를 노출해야 한다는 것입니다. 이 요구 사항을 지정하려면 제약 조건 목록에 `New` 제약 조건을 포함해야 합니다.  
  
 **오류 ID:** BC32083  
  
### 이 오류를 해결하려면  
  
1.  형식 인수의 형식 이름 및 제네릭 형식 이름을 제대로 입력했는지 확인합니다.  
  
2.  액세스 가능하고 매개 변수가 없는 생성자를 노출하는 형식 인수의 형식을 선택합니다. 이 형식 매개 변수에 이러한 형식 인수를 제공할 수 없는 경우 이 특정 제네릭 형식을 호출할 수 없습니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)   
 [방법: 제네릭 클래스 사용](../Topic/How%20to:%20Use%20a%20Generic%20Class%20\(Visual%20Basic\).md)