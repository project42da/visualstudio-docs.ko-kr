---
title: "&#39;&lt;procedurename&gt;&#39; 메서드에 대해 유추된 형식 인수가 다음 오류를 표시했습니다(&lt;errorlist&gt;). | Microsoft Docs"
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
  - "bc30954"
  - "vbc30954"
helpviewer_keywords: 
  - "BC30954"
ms.assetid: 796592c4-70b7-45be-9322-db09e9095d7d
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;procedurename&gt;&#39; 메서드에 대해 유추된 형식 인수가 다음 오류를 표시했습니다(&lt;errorlist&gt;).
제네릭 프로시저가 형식 인수를 제공하지 않고 호출되었으며 유추된 형식 인수로 인해 하나 이상의 제약 조건 위반이 발생합니다.  
  
 일반적으로 제네릭 형식을 호출하는 경우 제네릭 형식이 정의하는 각 형식 매개 변수에 대해 형식 인수를 제공합니다. 형식 인수를 제공하지 않으면 컴파일러에서 형식 매개 변수에 전달될 형식을 유추하려고 합니다. 유추된 형식이 하나 이상의 형식 매개 변수 제약 조건을 충족하지 않을 경우 컴파일러에서 이 오류를 생성합니다.  
  
 형식 매개 변수의 *제약 조건*은 전달할 수 있는 형식 인수를 제한합니다. 예를 들어 <xref:System.IComparable%601> 인터페이스를 구현하는 클래스로 형식 매개 변수를 제한할 수 있습니다. 자세한 내용은 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)에서 "제약 조건"을 참조하세요.  
  
 **오류 ID:** BC30954  
  
### 이 오류를 해결하려면  
  
-   컴파일러에서 유추할 필요가 없도록 제네릭 프로시저에 형식 인수를 제공합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)