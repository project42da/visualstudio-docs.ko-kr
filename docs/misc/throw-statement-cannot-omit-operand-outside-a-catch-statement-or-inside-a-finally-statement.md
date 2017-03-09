---
title: "&#39;Throw&#39; 문은 &#39;Catch&#39; 문 외부 또는 &#39;Finally&#39; 문 내부에서 피연산자를 생략할 수 없습니다. | Microsoft Docs"
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
  - "vbc30666"
  - "bc30666"
helpviewer_keywords: 
  - "BC30666"
ms.assetid: a208a6ea-0e36-4bf1-8984-4de1a0e38a2a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Throw&#39; 문은 &#39;Catch&#39; 문 외부 또는 &#39;Finally&#39; 문 내부에서 피연산자를 생략할 수 없습니다.
`Catch` 문 외부의 `Throw` 문에서 예외 개체의 이름을 제공해야 합니다.  
  
 **오류 ID:** BC30666  
  
### 이 오류를 해결하려면  
  
1.  `System.Exception`에서 파생된 예외 개체의 이름을 지정합니다.  
  
2.  `Throw` 문이 `Catch` 블록 내부에 있도록 코드를 재구성합니다.  
  
## 참고 항목  
 [Throw Statement](/dotnet/visual-basic/language-reference/statements/throw-statement)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Visual Basic의 예외 클래스](http://msdn.microsoft.com/ko-kr/9aac396f-34ca-4afb-8e6c-e523cb690ba9)   
 [Visual Basic에서 예외 및 오류 처리](http://msdn.microsoft.com/ko-kr/3e351e73-cf23-40ab-8b60-05794160529e)