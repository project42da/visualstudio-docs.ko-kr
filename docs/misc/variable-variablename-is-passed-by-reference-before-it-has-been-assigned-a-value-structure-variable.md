---
title: "&#39;&lt;variablename&gt;&#39; 변수에 값이 할당되기 전에 참조를 통해 변수(구조 변수)가 전달되었습니다. | Microsoft Docs"
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
  - "bc42108"
  - "vbc42108"
helpviewer_keywords: 
  - "BC42108"
ms.assetid: 8f858dd7-db04-408e-ae67-e4ff2f0e5e30
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;variablename&gt;&#39; 변수에 값이 할당되기 전에 참조를 통해 변수(구조 변수)가 전달되었습니다.
'\<variablename\>' 변수에 값이 할당되기 전에 참조를 통해 변수가 전달되었습니다. 런타임에 null 참조 예외가 발생할 수 있습니다. 사용하기 전에 구조체 또는 참조 멤버가 모두 초기화되었는지 확인합니다.  
  
 변수에 값을 할당하기 전에 프로시저 호출에서 구조 변수를 인수로 `ByRef` 매개 변수에 전달합니다.  
  
 구조체 변수에 값이 할당되지 않으면 각 구조체 멤버가 해당 데이터 형식에 대한 기본값을 유지합니다. 참조 데이터 형식의 경우 해당 기본값은 [Nothing](/dotnet/visual-basic/language-reference/nothing)입니다. 값이 `Nothing`인 참조 멤버를 읽으면 일부 환경에서 <xref:System.NullReferenceException>이 발생할 수 있습니다.  
  
 인수를 프로시저 `ByRef`에 전달하면 인수의 기반이 되는 변수를 노출하여 프로시저에서 수정할 수 있습니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42108  
  
### 이 오류를 해결하려면  
  
-   프로시저에서 `ByRef` 인수를 통해 값을 구조체 멤버에 할당하려는 경우 멤버에 이미 값이 있는지 여부가 중요하지 않으면 아무런 작업도 필요하지 않습니다.  
  
-   프로시저의 논리가 구조체 멤버를 읽은 후에 값을 할당하는 경우 멤버가 값 형식이면 프로시저 논리가 멤버의 자체 기본값 유지 여부에 종속되지 않아야 합니다.  
  
-   프로시저의 논리가 구조체 멤버를 읽은 후에 값을 할당하는 경우 멤버가 참조 형식이면 프로시저 논리가 `Nothing` 값을 처리할 수 있어야 합니다. 예를 들어 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)을 사용하여 <xref:System.NullReferenceException>를 catch할 수 있습니다.  
  
## 참고 항목  
 [Dim Statement](/dotnet/visual-basic/language-reference/statements/dim-statement)   
 [Value Types and Reference Types](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)   
 [Passing Arguments by Value and by Reference](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference)   
 [ByRef](/dotnet/visual-basic/language-reference/modifiers/byref)   
 [변수 선언](/dotnet/visual-basic/programming-guide/language-features/variables/variable-declaration)   
 [Structures](/dotnet/visual-basic/programming-guide/language-features/data-types/structures)   
 [Structure Statement](/dotnet/visual-basic/language-reference/statements/structure-statement)   
 [변수 문제 해결](/dotnet/visual-basic/programming-guide/language-features/variables/troubleshooting-variables)