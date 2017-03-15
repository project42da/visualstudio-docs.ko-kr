---
title: "제네릭 메서드에서는 &#39;Handles&#39; 절을 사용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32080"
  - "BC32080"
helpviewer_keywords: 
  - "BC32080"
ms.assetid: 88c62a1c-aee3-46b2-ad78-76790022c04c
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제네릭 메서드에서는 &#39;Handles&#39; 절을 사용할 수 없습니다.
제네릭 `Sub` 프로시저의 선언에 [Handles](/dotnet/visual-basic/language-reference/statements/handles-clause) 절이 포함되어 있습니다.  
  
 `Handles` 절은 `Sub` 프로시저가 처리하는 이벤트 목록을 지정합니다. 이벤트 처리기로 사용하려면 처리할 각 이벤트와 동일한 서명이 `Sub` 프로시저에 있어야 합니다. 제네릭 프로시저는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]가 컴파일 시간에 예측할 수 없는 서명을 사용하여 두 번 이상 만들 수 있습니다. 따라서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]는 서명이 `Handles` 절의 이벤트 서명과 일치한다고 보장할 수 없습니다.  
  
 **오류 ID:** BC32080  
  
### 이 오류를 해결하려면  
  
-   `Sub` 프로시저가 제네릭이어야 하는 경우 해당 선언에서 `Handles` 절을 제거합니다.[AddHandler Statement](/dotnet/visual-basic/language-reference/statements/addhandler-statement)을 사용하여 이 이벤트 처리기를 이벤트와 연결합니다.  
  
-   `Sub` 프로시저에서 `Handles` 절을 사용하여 이벤트를 연결해야 하는 경우 해당 선언에서 [Of](/dotnet/visual-basic/language-reference/statements/of-clause) 절을 제거합니다.`Handles`를 사용할 때는 제네릭이 아닌 프로시저를 사용해야 합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [빌드에 없음: 이벤트 및 이벤트 처리기](http://msdn.microsoft.com/ko-kr/95074a0d-1cbc-4221-a95a-964185c7f962)