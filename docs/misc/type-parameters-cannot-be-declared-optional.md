---
title: "&lt;type&gt; 매개 변수는 &#39;Optional&#39;로 선언할 수 없습니다. | Microsoft Docs"
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
  - "bc33010"
  - "vbc33010"
helpviewer_keywords: 
  - "BC33010"
ms.assetid: ec4023e7-9ba6-4532-a6b9-4ae6b4f9063a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;type&gt; 매개 변수는 &#39;Optional&#39;로 선언할 수 없습니다.
대리자, 이벤트 또는 연산자의 정의가 [Optional](/dotnet/visual-basic/language-reference/modifiers/optional) 매개 변수를 선언합니다.  
  
 `Optional` 매개 변수는 `Declare`, `Function`, `Property` 및 `Sub` 매개 변수에서만 사용할 수 있습니다.  
  
 **오류 ID:** BC33010  
  
### 이 오류를 해결하려면  
  
-   매개 변수 목록에서 `Optional` 키워드를 제거합니다.  
  
-   연산자를 정의하는 경우 일련의 오버로드가 있는 `Optional` 기능을 사용할 수 있습니다.  
  
-   대리자 또는 이벤트를 정의하는 경우 응용 프로그램의 이 부분에 대한 전체 논리를 다시 작업해야 합니다. 대리자 또는 이벤트 매개 변수에서 `Optional`이나 [ParamArray](/dotnet/visual-basic/language-reference/modifiers/paramarray) 매개 변수 또는 오버로드된 버전을 사용할 수 없습니다.  
  
## 참고 항목  
 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)   
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)