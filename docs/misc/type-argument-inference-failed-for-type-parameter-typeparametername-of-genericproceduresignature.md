---
title: "&#39;&lt;genericproceduresignature&gt;&#39;의 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;의 형식 인수를 유추하지 못했습니다. | Microsoft Docs"
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
  - "vbc32051"
  - "bc32051"
helpviewer_keywords: 
  - "BC32051"
ms.assetid: a9c2a0ce-e225-4549-bfd8-d42df5d16bfd
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;genericproceduresignature&gt;&#39;의 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;의 형식 인수를 유추하지 못했습니다.
'\<genericproceduresignature\>'의 형식 매개 변수 '\<typeparametername\>'의 형식 인수를 유추하지 못했습니다. '\<parametername\>' 매개 변수에 전달된 인수에서 형식 인수를 유추할 수 없습니다.  
  
 제네릭 프로시저가 형식 인수 제공 없이 호출되고 컴파일러에서 매개 변수 중 하나에 전달할 형식을 유추할 수 없습니다.  
  
 일반적으로 제네릭 프로시저를 호출하는 경우 제네릭 프로시저가 정의하는 각 형식 매개 변수에 대해 형식 인수를 제공합니다. 형식 인수를 제공하지 않으면 컴파일러에서 형식 매개 변수에 전달될 형식을 유추하려고 합니다. 호출 컨텍스트에서 형식 매개 변수에 대한 충돌 데이터 형식 정보를 제공하는 경우 형식 유추가 실패합니다.  
  
 다음 코드에서는 이 오류를 생성할 수 있습니다.  
  
```  
Public Sub doSomething(Of t)(ByVal arg1 As t(), ByVal arg2 As t) End Sub Call doSomething(6, 42)  
```  
  
 앞의 예제에서 컴파일러는 `arg2`에 전달된 값 42를 기준으로 `t`에 대한 형식 `Integer`를 유추합니다. 그러나 이렇게 유추하기 위해서는 `arg1`의 형식이 `Integer()`여야 합니다. 즉, `Integer` 배열과 `arg1`에 전달된 값 6이 해당 형식과 일치하지 않습니다.  
  
 **오류 ID:** BC32051  
  
### 이 오류를 해결하려면  
  
-   컴파일러에서 유추할 필요가 없도록 제네릭 프로시저에 형식 인수를 제공합니다.  
  
-   형식 인수와 일치하는 형식의 일반 인수를 제공합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)