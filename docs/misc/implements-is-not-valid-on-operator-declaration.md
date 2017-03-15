---
title: "연산자 선언에는 &#39;Implements&#39;를 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc33004"
  - "bc33004"
helpviewer_keywords: 
  - "BC33004"
ms.assetid: 22f27f4d-4bbd-4f8f-a6e8-0fc10efb268d
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연산자 선언에는 &#39;Implements&#39;를 사용할 수 없습니다.
[Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)은 [Implements](/dotnet/visual-basic/language-reference/statements/implements-clause) 키워드를 지정합니다.  
  
 `Function` 또는 `Sub` 프로시저, 속성 또는 이벤트만 인터페이스 멤버를 구현할 수 있습니다. 구현에 대한 자세한 내용은 [빌드에 없음: Visual Basic의 인터페이스 구현 예제](http://msdn.microsoft.com/ko-kr/50bf2a30-73b6-4126-a921-075fd6eec278)를 참조하세요.  
  
 `Operator` 프로시저에는 `Public` 및 `Shared` 키워드가 모두 필요하며 변환 연산자에는 `Widening` 또는 `Narrowing` 키워드가 필요합니다. 자세한 내용은 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)을 참조하세요.  
  
 **오류 ID:** BC33004  
  
### 이 오류를 해결하려면  
  
-   이 프로시저가 인터페이스 멤버를 구현하려면 프로시저를 `Function` 또는 `Sub` 프로시저, 속성 또는 이벤트로 다시 작성합니다.  
  
-   이 프로시저가 연산자를 정의하려면 프로시저의 선언에서 `Implements` 키워드를 제거합니다.  
  
## 참고 항목  
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)