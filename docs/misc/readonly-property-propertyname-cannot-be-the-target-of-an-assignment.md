---
title: "&#39;ReadOnly&#39; 속성 &#39;&lt;propertyname&gt;&#39;은 할당 대상일 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30098"
  - "vbc30098"
helpviewer_keywords: 
  - "BC30098"
ms.assetid: d0c6cdac-a49d-49d2-ba92-ddf01eed0620
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ReadOnly&#39; 속성 &#39;&lt;propertyname&gt;&#39;은 할당 대상일 수 없습니다.
`ReadOnly` 속성은 값을 할당하는 컨텍스트에서 발생합니다. 쓰기 가능한 변수, 속성 및 배열 요소만 실행 중 할당되는 값을 가질 수 있습니다.  
  
 **오류 ID:** BC30098  
  
### 이 오류를 해결하려면  
  
-   변수 선언 중 `Property` 문에서 `ReadOnly` 키워드를 제거하거나 값을 할당하는 문을 제거합니다.  
  
## 참고 항목  
 [ReadOnly](/dotnet/visual-basic/language-reference/modifiers/readonly)   
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)