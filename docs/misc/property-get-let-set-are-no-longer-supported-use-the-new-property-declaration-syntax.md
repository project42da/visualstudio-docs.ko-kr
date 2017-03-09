---
title: "Property Get/Let/Set이 더 이상 지원되지 않으므로 새 Property 선언 구문을 사용하세요. | Microsoft Docs"
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
  - "vbc30808"
  - "bc30808"
helpviewer_keywords: 
  - "BC30808"
ms.assetid: c8a803eb-316d-4f73-b6ef-27a2914409f3
caps.latest.revision: 10
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Property Get/Let/Set이 더 이상 지원되지 않으므로 새 Property 선언 구문을 사용하세요.
`Property Get/Let/Set`은 더 이상 지원되지 않습니다. 새로운 `Property` 선언 구문을 사용합니다.  
  
 속성 선언 구문이 변경되었습니다. 이제 속성이 블록 내에서 정의됩니다.  
  
 **오류 ID:** BC30808  
  
### 이 오류를 해결하려면  
  
1.  `Property` 키워드로 시작하는 코드 블록에서 속성을 정의합니다.`End Property` 구문을 사용하여 속성을 종료합니다.  
  
2.  `Get` 키워드를 사용하여 속성 블록 내에서 `Get` 속성 프로시저를 정의합니다.`End Get` 구문을 사용하여 `Get` 속성 프로시저를 종료합니다.  
  
3.  `Set` 키워드를 사용하여 속성 블록 내에서 `Set` 속성 프로시저를 정의합니다.`End Set` 구문을 사용하여 `Set` 속성 프로시저를 종료합니다.  
  
4.  모든 속성 할당에 대해 `Set` 속성 프로시저를 사용합니다.`Let` 속성 프로시저는 더 이상 필요하지 않거나 지원되지 않습니다.  
  
## 참고 항목  
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Language Changes in Visual Basic](http://msdn.microsoft.com/ko-kr/a1be4461-a0e4-4a88-a32c-dcad41ed119a)