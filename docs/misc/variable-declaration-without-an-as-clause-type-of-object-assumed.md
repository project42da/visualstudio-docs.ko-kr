---
title: "변수 선언에 &#39;As&#39; 절이 없습니다. Object 형식으로 간주합니다. | Microsoft Docs"
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
  - "BC42020"
  - "vbc42020"
helpviewer_keywords: 
  - "BC42020"
ms.assetid: 9422b16d-39b5-4d49-b697-608226ccafea
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 변수 선언에 &#39;As&#39; 절이 없습니다. Object 형식으로 간주합니다.
변수 선언이 `As` 절을 지정하지 않습니다.  
  
 `As` 절은 프로그래밍 요소와 연결될 데이터 형식을 식별합니다.[Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)에서 변수의 데이터 형식을 지정합니다.`Dim` 문에 `As` 절이 없는 경우 변수 데이터 형식의 기본값은 `Object`입니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42020  
  
### 이 오류를 해결하려면  
  
-   `Dim` 문에 `As` 절을 포함하여 변수의 데이터 형식을 지정합니다.  
  
## 참고 항목  
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [변수 선언](/dotnet/visual-basic/programming-guide/language-features/variables/variable-declaration)