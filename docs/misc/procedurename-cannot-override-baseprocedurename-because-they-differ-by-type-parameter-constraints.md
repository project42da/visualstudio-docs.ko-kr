---
title: "형식 매개 변수 제약 조건이 서로 다르므로 &#39;&lt;procedurename&gt;&#39;은(는) &#39;&lt;baseprocedurename&gt;&#39;을 재정의할 수 없습니다. | Microsoft Docs"
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
  - "BC32077"
  - "vbc32077"
helpviewer_keywords: 
  - "BC32077"
ms.assetid: 9be1a88d-c1a4-4f12-8e72-74abb2be565d
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 매개 변수 제약 조건이 서로 다르므로 &#39;&lt;procedurename&gt;&#39;은(는) &#39;&lt;baseprocedurename&gt;&#39;을 재정의할 수 없습니다.
제네릭 프로시저가 제네릭 기본 클래스 프로시저를 재정의하려고 하지만 해당 형식 매개 변수의 제약 조건 목록이 서로 다릅니다.  
  
 기본 클래스 프로시저를 재정의하려면 재정의하는 프로시저가 기본 클래스 프로시저의 전체 서명뿐 아니라 프로시저의 액세스 수준 및 각 매개 변수의 전달 메커니즘이 일치해야 합니다.  
  
 제네릭 기본 클래스 프로시저를 재정의하려면 재정의하는 프로시저가 형식 매개 변수 개수 및 각 형식 매개 변수의 제약 조건 목록도 일치해야 합니다.  
  
 재정의 요구 사항에 대한 자세한 내용은 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides)를 참조하세요.  
  
 **오류 ID:** BC32077  
  
### 이 오류를 해결하려면  
  
-   기본 클래스 프로시저를 재정의하려는 경우 형식 매개 변수 제약 조건을 기본 클래스 프로시저와 정확히 일치하도록 수정합니다.  
  
-   형식 매개 변수 제약 조건을 원래대로 유지해야 하는 경우에는 기본 클래스 프로시저를 재정의할 수 없습니다. 선언에서 `Overrides` 키워드를 제거합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)