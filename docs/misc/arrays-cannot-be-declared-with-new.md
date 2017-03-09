---
title: "배열은 &#39;New&#39;로 선언할 수 없습니다. | Microsoft Docs"
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
  - "vbc30053"
  - "bc30053"
helpviewer_keywords: 
  - "BC30053"
ms.assetid: aa55f3b7-2045-497b-9543-5ec6e2b74fe2
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 배열은 &#39;New&#39;로 선언할 수 없습니다.
`New` 키워드는 배열 선언의 초기화 부분에만 나타날 수 있습니다. 즉, `New`가 등호\(`=`\) 오른쪽에 있어야 배열 변수에 할당될 새 배열 형식을 만들 수 있습니다.  
  
 클래스 초기화에 대한 바로 가기는 배열에 사용할 수 없습니다. 다음 두 코드 줄은 클래스에서 개체를 초기화하기 때문에 모두 유효하고 동일합니다.  
  
```  
Dim formA as Form = New Form Dim formA as New Form  
```  
  
 그러나 배열 초기화는 클래스 초기화와 같은 바로 가기를 사용할 수 없습니다.  
  
 배열의 `New` 절에는 괄호 `()` 및 중괄호 `{}`가 모두 있어야 합니다. 괄호는 새 형식을 배열로 지정하고 중괄호는 초기화 값을 제공합니다. 배열 값이 비어 있는 경우, 즉 배열 값을 초기화하지 않는 경우에도 컴파일러에는 괄호가 필요합니다.  
  
 **오류 ID:** BC30053  
  
### 이 오류를 해결하려면  
  
-   `Dim myDates() As New Date`와 같은 문을 `Dim myDates() As Date = New Date() {}`와 같은 문으로 바꿉니다.  
  
## 참고 항목  
 [배열](/dotnet/visual-basic/programming-guide/language-features/arrays/index)   
 [How to: Initialize an Array Variable in Visual Basic](../Topic/How%20to:%20Initialize%20an%20Array%20Variable%20in%20Visual%20Basic.md)