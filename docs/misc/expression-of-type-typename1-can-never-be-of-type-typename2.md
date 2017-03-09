---
title: "&#39;&lt;typename1&gt;&#39; 형식의 식은 &#39;&lt;typename2&gt;&#39; 형식일 수 없습니다. | Microsoft Docs"
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
  - "vbc31430"
  - "bc31430"
helpviewer_keywords: 
  - "BC31430"
ms.assetid: 1d527033-3f6f-4945-b1d3-5ef59a1e1b53
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename1&gt;&#39; 형식의 식은 &#39;&lt;typename2&gt;&#39; 형식일 수 없습니다.
`TypeOf`...`Is` 식은 유지할 수 없는 데이터 형식에 대한 개체 참조 변수를 테스트합니다.  
  
 일부 경우 컴파일러에서 `TypeOf`...`Is` 테스트는 실패만 할 수 있다고 결정할 수 있습니다\(예: 두 클래스 간의 상속 관계가 없는 경우\).  
  
 다음 코드에서는 이 오류를 생성할 수 있습니다.  
  
 `Dim refVar as System.Windows.Forms.Form`  
  
 `If TypeOf refVar Is System.Array`  
  
 `End If`  
  
 <xref:System.Windows.Forms.Form>과 <xref:System.Array>는 전혀 관련이 없는 형식이기 때문에 컴파일러가 `TypeOf`...`Is` 식이 `refVar`의 값에 대해 `False`를 반환한다는 것을 결정할 수 있습니다.  
  
 **오류 ID:** BC31430  
  
### 이 오류를 해결하려면  
  
-   실제 데이터 형식에 대한 변수를 테스트하거나 `TypeOf`...`Is` 테스트를 완전히 제거합니다.  
  
## 참고 항목  
 [TypeOf Operator](/dotnet/visual-basic/language-reference/operators/typeof-operator)   
 [How to: Determine What Type an Object Variable Refers To](../Topic/How%20to:%20Determine%20What%20Type%20an%20Object%20Variable%20Refers%20To%20\(Visual%20Basic\).md)