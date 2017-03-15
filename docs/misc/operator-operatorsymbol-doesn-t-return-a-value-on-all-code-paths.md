---
title: "&#39;&lt;operatorsymbol&gt;&#39; 연산자가 일부 코드 경로에 대해서만 값을 반환합니다. | Microsoft Docs"
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
  - "vbc42106"
  - "bc42106"
helpviewer_keywords: 
  - "BC42106"
ms.assetid: 175b2bc9-5233-462d-97de-9d97b003cc46
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;operatorsymbol&gt;&#39; 연산자가 일부 코드 경로에 대해서만 값을 반환합니다.
'\<operatorsymbol\>' 연산자가 일부 코드 경로에 대해서만 값을 반환합니다. 이 결과를 사용하면 런타임에 null 참조 예외가 발생할 수 있습니다.  
  
 연산자 프로시저에 해당 코드를 통해 값을 반환하지 않는 하나 이상의 경로가 있습니다.  
  
 [Return Statement](/dotnet/visual-basic/language-reference/statements/return-statement)에 포함하는 방법으로만 연산자 프로시저에서 값을 반환할 수 있습니다.  
  
 컨트롤을 `End Operator` 문에 전달하는 경우 연산자 프로시저는 속성 데이터 형식의 기본값을 반환합니다. 자세한 내용은 [Function Statement](/dotnet/visual-basic/language-reference/statements/function-statement)의 "동작"을 참조하세요.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42106  
  
### 이 오류를 해결하려면  
  
-   제어 흐름 논리를 검사하고 모든 가능한 경로가 `Return` 문으로 끝나는지 확인합니다. 특히, `End Operator` 앞의 마지막 문이 `Return` 문이어야 합니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)