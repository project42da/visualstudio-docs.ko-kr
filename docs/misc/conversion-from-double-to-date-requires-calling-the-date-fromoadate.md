---
title: "&#39;Double&#39;을 &#39;Date&#39;로 변환하려면 &#39;Date.FromOADate&#39;를 호출해야 합니다. | Microsoft Docs"
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
  - "vbc30533"
  - "bc30533"
helpviewer_keywords: 
  - "BC30533"
ms.assetid: afcfd115-4614-4b0b-ad09-76af8dba2ed5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Double&#39;을 &#39;Date&#39;로 변환하려면 &#39;Date.FromOADate&#39;를 호출해야 합니다.
`Date` 값을 `Double` 값에 캐스트하려고 했지만 <xref:System.DateTime.FromOADate%2A?displayProperty=fullName> 메서드를 사용하지 않고 수행될 수 없습니다.  
  
 **오류 ID:** BC30533  
  
### 이 오류를 해결하려면  
  
-   <xref:System.DateTime.FromOADate%2A> 메서드를 사용하여 값을 변환합니다.  
  
## 참고 항목  
 [Type Conversions in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/type-conversions)