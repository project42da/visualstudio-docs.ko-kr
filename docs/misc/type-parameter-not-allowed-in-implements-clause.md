---
title: "&#39;Implements&#39; 절에는 형식 매개 변수를 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc32056"
  - "bc32056"
helpviewer_keywords: 
  - "BC32056"
ms.assetid: a62d773b-e878-4817-8638-da49849477d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Implements&#39; 절에는 형식 매개 변수를 사용할 수 없습니다.
제네릭 형식의 `Implements` 절은 구현할 멤버로 형식 매개 변수를 지정합니다.  
  
 `Implements` 절은 인터페이스와 멤버를 지정해야 합니다. 형식 매개 변수를 인터페이스로 전달할 수 있지만 멤버로 전달하거나 멤버 이름으로 사용할 수는 없습니다.  
  
 다음 문은 이 오류를 생성할 수 있습니다.  
  
```  
Class c1(Of t) Implements i1(Of t) Public Sub doSomething() Implements t End Class  
```  
  
 **오류 ID:** BC32056  
  
### 이 오류를 해결하려면  
  
-   `Implements` 키워드 뒤에 인터페이스 이름 및 인터페이스의 정규 멤버를 지정합니다. 해당하는 경우 인터페이스에 형식 매개 변수를 전달할 수 있습니다.  
  
    ```  
    Public Sub doSomething() Implements i1(Of t).doSomething  
    ```  
  
## 참고 항목  
 [Implements](/dotnet/visual-basic/language-reference/statements/implements-clause)   
 [빌드에 없음: Implements 키워드 및 Implements 문](http://msdn.microsoft.com/ko-kr/b96560f7-6413-480f-a1e2-f80253bab5be)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)