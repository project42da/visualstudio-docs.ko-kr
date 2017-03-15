---
title: "&#39;AddHandler&#39; 또는 &#39;RemoveHandler&#39; 문의 이벤트 피연산자는 점으로 한정된 식이거나 단순한 이름이어야 합니다. | Microsoft Docs"
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
  - "vbc30677"
  - "bc30677"
helpviewer_keywords: 
  - "BC30677"
ms.assetid: b71eb2f0-0bb2-4aeb-94ec-5c37ab960d9e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;AddHandler&#39; 또는 &#39;RemoveHandler&#39; 문의 이벤트 피연산자는 점으로 한정된 식이거나 단순한 이름이어야 합니다.
이벤트 인수에 대해 `AddHandler` 또는 `RemoveHandler`로 지정된 항목이 이벤트로 인식되지 않습니다.  
  
 **오류 ID:** BC30677  
  
### 이 오류를 해결하려면  
  
-   다음 예제와 같이 뒤에 점\(`.`\)이 오는 이벤트를 발생시키는 개체의 이름과 이벤트 이름을 지정합니다.  
  
     [!CODE [VbVbalrEventError#30](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#30)]  
  
## 참고 항목  
 [AddHandler Statement](/dotnet/visual-basic/language-reference/statements/addhandler-statement)   
 [RemoveHandler Statement](/dotnet/visual-basic/language-reference/statements/removehandler-statement)   
 [빌드에 없음: AddHandler 및 RemoveHandler](http://msdn.microsoft.com/ko-kr/a7a24bd2-519a-46fe-8a2c-2b9df2ca28ef)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)