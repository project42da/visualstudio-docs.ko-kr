---
title: "&#39;ReDim&#39;으로는 맨 오른쪽 차원만 변경할 수 있습니다. | Microsoft Docs"
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
  - "vbrArray_TypeMismatch"
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ReDim&#39;으로는 맨 오른쪽 차원만 변경할 수 있습니다.
`ReDim` 문에서 `Preserve` 키워드를 사용하여 마지막 차원이 아닌 배열의 차원을 변경하려고 했습니다.`Preserve`를 사용하는 경우 배열의 마지막 차원만 크기를 조정할 수 있습니다. 다른 모든 차원의 경우 기존 배열과 동일한 크기를 지정해야 합니다.  
  
### 이 오류를 해결하려면  
  
-   `Preserve` 키워드를 제거합니다.  
  
## 참고 항목  
 [NOTINBUILD Visual Basic의 배열 개요](http://msdn.microsoft.com/ko-kr/ca50e2f2-b4d2-4c57-9169-9abbcc3392d8)   
 [NOTINBUILD Visual Basic의 다차원 배열](http://msdn.microsoft.com/ko-kr/d92cad25-07e2-4d79-8ea4-ab269700f5de)   
 [ReDim Statement](/dotnet/visual-basic/language-reference/statements/redim-statement)   
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [Preserve \- 삭제](http://msdn.microsoft.com/ko-kr/91badeab-b4e0-48b6-92c9-9f0c8f995d81)