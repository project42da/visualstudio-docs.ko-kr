---
title: "&#39;ReadOnly&#39; 변수는 할당 대상일 수 없습니다. | Microsoft Docs"
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
  - "vbc30064"
  - "bc30064"
helpviewer_keywords: 
  - "BC30064"
ms.assetid: 17e0751d-4c22-40b2-bb07-cb5c845dbc30
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ReadOnly&#39; 변수는 할당 대상일 수 없습니다.
`ReadOnly` 속성이 해당 값을 할당하는 컨텍스트에 있습니다. 쓰기 가능한 변수, 속성 및 배열 요소만 실행 중 할당되는 값을 가질 수 있습니다.  
  
 **오류 ID:** BC30064  
  
### 이 오류를 해결하려면  
  
-   변수 선언 중 `Dim` 문에서 `ReadOnly` 키워드를 제거하거나 값을 할당하는 문을 제거합니다.  
  
## 참고 항목  
 [ReadOnly](/dotnet/visual-basic/language-reference/modifiers/readonly)   
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)