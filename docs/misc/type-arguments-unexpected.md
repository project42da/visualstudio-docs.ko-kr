---
title: "예기치 않은 형식 인수입니다. | Microsoft Docs"
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
  - "vbc32088"
  - "bc32088"
helpviewer_keywords: 
  - "BC32088"
ms.assetid: a0918e90-e7ad-4edc-81e1-584e6174bb6c
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 예기치 않은 형식 인수입니다.
`Implements` 절은 구현하는 인터페이스 멤버에 대한 형식 인수를 제공합니다.  
  
 `Implements` 절은 구현하는 인터페이스와 멤버만 식별해야 합니다. 즉, 제네릭 프로시저를 선언하는 경우 인터페이스 프로시저를 구현하지 않는 경우처럼 `Of` 절과 형식 인수를 선언의 main 부분에 사용해야 합니다.  
  
 다음 코드에서는 이 오류를 생성할 수 있습니다.  
  
```  
Public Interface testInterface Sub testSub(Of t)() End Interface Public Class testClass Implements testInterface Public Sub testSub() Implements testInterface.testSub(Of t)() End Sub End Class  
```  
  
 `Implements` 절 앞의 선언은 액세스 또는 프로시저 한정자가 추가될 수 있다는 점을 제외하고 인터페이스 정의처럼 표시되어야 합니다. 다음 코드에서는 오류를 방지합니다.  
  
```  
Public Sub testSub(Of t)() Implements testInterface.testSub  
```  
  
 **오류 ID:** BC32088  
  
### 이 오류를 해결하려면  
  
-   `Implements` 절에서 형식 인수 목록을 제거합니다.  
  
-   인터페이스의 제네릭 멤버를 구현하는 경우 `Implements` 키워드 앞에 오는 선언의 main 부분에 형식 인수 목록을 추가합니다.  
  
## 참고 항목  
 [Implements](/dotnet/visual-basic/language-reference/statements/implements-clause)   
 [빌드에 없음: Implements 키워드 및 Implements 문](http://msdn.microsoft.com/ko-kr/b96560f7-6413-480f-a1e2-f80253bab5be)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)