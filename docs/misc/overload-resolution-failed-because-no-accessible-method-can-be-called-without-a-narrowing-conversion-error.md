---
title: "형식을 축소 변환하지 않고 호출할 수 있는 액세스 가능한 &#39;&lt;method&gt;&#39;가 없으므로 오버로드 확인에 실패했습니다. &lt;error&gt; | Microsoft Docs"
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
  - "vbc30519"
  - "bc30519"
helpviewer_keywords: 
  - "BC30519"
ms.assetid: 3b3e724d-6fad-4146-b47d-6525493b2fa8
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식을 축소 변환하지 않고 호출할 수 있는 액세스 가능한 &#39;&lt;method&gt;&#39;가 없으므로 오버로드 확인에 실패했습니다. &lt;error&gt;
오버로드된 메서드를 호출했지만 컴파일러에서 축소 변환 없이 호출할 수 있는 메서드를 찾을 수 없습니다. 축소 변환은 가능한 값의 일부를 정확하게 저장하지 못할 수도 있는 데이터 형식으로 값을 변경합니다.  
  
 **오류 ID:** BC30519  
  
### 이 오류를 해결하려면  
  
-   `Option Strict Off`을 지정합니다.  
  
## 참고 항목  
 [Overloaded Properties and Methods](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/overloaded-properties-and-methods)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)