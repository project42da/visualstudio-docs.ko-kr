---
title: "지정한 개수의 형식 인수를 허용하는 액세스 가능한 &#39;&lt;genericprocedurename&gt;&#39;이 없으므로 오버로드 확인에 실패했습니다. | Microsoft Docs"
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
  - "bc32087"
  - "vbc32087"
helpviewer_keywords: 
  - "BC32087"
ms.assetid: a3eaafd3-80f6-4b7d-9b75-47b043fe17b5
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 지정한 개수의 형식 인수를 허용하는 액세스 가능한 &#39;&lt;genericprocedurename&gt;&#39;이 없으므로 오버로드 확인에 실패했습니다.
컴파일러가 적절한 개수의 형식 매개 변수를 사용하여 오버로드된 버전에 액세스할 수 없으므로 오버로드된 제네릭 프로시저 호출을 확인할 수 없습니다.  
  
 제네릭 프로시저를 호출하는 경우 각 형식 매개 변수에 대해 하나의 형식 인수를 제공해야 합니다. 또는 형식 인수를 제공하지 않고 컴파일러에서 *형식 유추*를 수행하도록 할 수 있습니다. 자세한 내용은 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)의 "형식 유추"를 참조하세요.  
  
 **오류 ID:** BC32087  
  
### 이 오류를 해결하려면  
  
1.  호출 코드에서 호출하려는 버전에 액세스할 수 있는지 확인합니다.[Access Levels in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/access-levels)을 참조하세요.  
  
2.  형식 인수 목록이 호출하려는 버전의 형식 매개 변수 목록과 일치하도록 호출 코드에서 형식 인수를 추가하거나 제거합니다.  
  
     또는  
  
     호출 코드에서 모든 형식 인수를 제거하고 컴파일러에서 형식 유추를 수행하도록 합니다. 충돌 또는 모호성이 있을 경우 형식 유추에 실패할 수 있습니다.  
  
## 참고 항목  
 [Overloaded Properties and Methods](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/overloaded-properties-and-methods)   
 [Overload Resolution](/dotnet/visual-basic/programming-guide/language-features/procedures/overload-resolution)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)