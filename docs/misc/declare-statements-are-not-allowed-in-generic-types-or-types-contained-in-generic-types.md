---
title: "제네릭 형식 또는 제네릭 형식에 포함된 형식에는 &#39;Declare&#39; 문을 사용할 수 없습니다. | Microsoft Docs"
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
  - "BC32075"
  - "vbc32075"
helpviewer_keywords: 
  - "BC32075"
ms.assetid: c620b67e-70f8-42ac-8292-e9ea484904c3
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제네릭 형식 또는 제네릭 형식에 포함된 형식에는 &#39;Declare&#39; 문을 사용할 수 없습니다.
`Declare` 문이 제네릭 클래스 또는 구조체나 제네릭 클래스 또는 구조체 내에 선언된 클래스 또는 구조체의 일부로 사용되었습니다.  
  
 Visual Basic 및 .NET Framework는 현재 외부 참조와 제네릭 형식의 조합을 지원하지 않습니다. 컴파일러가 올바르게 호출하려면 모든 매개 변수 및 외부 프로시저의 반환 형식이 있어야 합니다.  
  
 **오류 ID:** BC32075  
  
### 이 오류를 해결하려면  
  
-   `Declare` 문을 제네릭 형식의 범위 외부로 이동하거나 완전히 제거합니다.  
  
## 참고 항목  
 [Declare Statement](/dotnet/visual-basic/language-reference/statements/declare-statement)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)