---
title: "&#39;&lt;type1&gt;&#39; 형식의 값을 &#39;&lt;type2&gt;&#39;로 변환할 수 없습니다. | Microsoft Docs"
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
  - "bc30311"
  - "vbc30311"
helpviewer_keywords: 
  - "BC30311"
ms.assetid: e3a513d4-2a1e-46d6-b592-b2e756b89d7d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;type1&gt;&#39; 형식의 값을 &#39;&lt;type2&gt;&#39;로 변환할 수 없습니다.
문에서 정의되지 않은 방식으로 하나의 데이터 형식을 다른 데이터 형식으로 변환하려고 합니다. 이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   변환은 서로 변환할 수 없는 두 데이터 형식을 지정합니다.`Boolean` 값을 `Date` 형식으로 변환하는 예제입니다.  
  
-   배열의 초기화는 `New` 절 다음에 중괄호\(`{}`\)를 포함하지 않습니다. 이 경우 \<type2\>는 '\<type\>의 1차원 배열' 형식입니다.  
  
 **오류 ID:** BC30311  
  
### 이 오류를 해결하려면  
  
-   식이 대상 데이터 형식으로 변환될 수 있어야 합니다.  
  
-   \<type2\>가 배열이면 `New` 절에 형식 이름 다음에 괄호와 중괄호 모두 포함되어 있어야 합니다. 다음 코드는 올바른 배열 초기화를 보여 줍니다.  
  
    ```  
    Dim anIntArray As Integer() = New Integer() {}  
    ```  
  
## 참고 항목  
 [Type Conversions in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/type-conversions)   
 [How to: Initialize an Array Variable in Visual Basic](../Topic/How%20to:%20Initialize%20an%20Array%20Variable%20in%20Visual%20Basic.md)