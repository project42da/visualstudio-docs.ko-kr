---
title: "연산자에 &#39;As&#39; 절이 없습니다. Object 형식으로 간주합니다. | Microsoft Docs"
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
  - "vbc41005"
  - "bc41005"
helpviewer_keywords: 
  - "BC41005"
ms.assetid: 42be84ed-7aa6-4ac0-9dd4-663e90f13e09
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연산자에 &#39;As&#39; 절이 없습니다. Object 형식으로 간주합니다.
연산자 프로시저에서 `As` 절을 지정하지 않습니다.  
  
 `As` 절은 프로그래밍 요소와 연결될 데이터 형식을 식별합니다.[Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)에서는 연산자 프로시저가 호출 코드에 반환하는 값의 데이터 형식을 지정합니다.`Operator` 문에 `As` 절이 없는 경우 반환 데이터 형식의 기본값은 `Object`입니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC41005  
  
### 이 오류를 해결하려면  
  
-   `Operator` 문에 `As` 절을 포함하여 반환 데이터 형식을 지정합니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)