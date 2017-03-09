---
title: "속성에 &#39;As&#39; 절이 없습니다. Object 형식으로 간주합니다. | Microsoft Docs"
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
  - "BC42022"
  - "vbc42022"
helpviewer_keywords: 
  - "BC42022"
ms.assetid: 3379692b-8278-4488-878a-0afb76e554b1
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 속성에 &#39;As&#39; 절이 없습니다. Object 형식으로 간주합니다.
속성 선언에서 `As` 절을 지정하지 않습니다.  
  
 `As` 절은 프로그래밍 요소와 연결될 데이터 형식을 식별합니다.[Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)에서는 속성의 `Get` 프로시저가 호출 코드에 반환하는 값의 데이터 형식을 지정합니다.`Property` 문에 `As` 절을 포함하지 않으면 속성의 데이터 형식이 기본적으로 `Object`로 설정됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42022  
  
### 이 오류를 해결하려면  
  
-   `Property` 문에 `As` 절을 포함하여 속성의 데이터 형식을 지정합니다.  
  
## 참고 항목  
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)   
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement)