---
title: "부분 메서드(Partial Method)는 Sub여야 하므로 &#39;&lt;elementname&gt;&#39;은 &#39;Partial&#39;로 선언할 수 없습니다. | Microsoft Docs"
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
  - "vbc31437"
  - "bc31437"
helpviewer_keywords: 
  - "BC31437"
ms.assetid: 31ca12ab-2c26-4907-a253-e7c57bb4f34b
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 부분 메서드(Partial Method)는 Sub여야 하므로 &#39;&lt;elementname&gt;&#39;은 &#39;Partial&#39;로 선언할 수 없습니다.
`Sub` 프로시저만 부분 메서드\(Partial Method\)를 선언할 수 있습니다. 예를 들어 다음 코드는 `partialMethod`가 함수이기 때문에 이 오류를 생성합니다.  
  
```  
' Partial Private Function partialMethod(ByVal n As Integer) As Integer ' End Function  
```  
  
 **오류 ID:** BC31437  
  
### 이 오류를 해결하려면  
  
-   부분 메서드\(Partial Method\)로 선언하는 항목을 `Sub`로 변환합니다.  
  
-   이 경우 부분 메서드\(Partial Method\)를 사용하지 마세요.  
  
## 참고 항목  
 [Partial Methods](/dotnet/visual-basic/programming-guide/language-features/procedures/partial-methods)   
 [Sub Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/sub-procedures)