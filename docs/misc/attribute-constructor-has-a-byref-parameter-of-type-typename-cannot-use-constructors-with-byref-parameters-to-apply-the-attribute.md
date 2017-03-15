---
title: "특성 생성자에 &#39;ByRef&#39; 매개 변수 형식 &#39;&lt;typename&gt;&#39;이 있으므로 byref 매개 변수와 함께 생성자를 사용하여 특성을 적용할 수 없습니다. | Microsoft Docs"
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
  - "bc36006"
  - "vbc36006"
helpviewer_keywords: 
  - "BC36006"
ms.assetid: 4c4e991f-3839-4196-bcfb-eb8464aa55e5
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 특성 생성자에 &#39;ByRef&#39; 매개 변수 형식 &#39;&lt;typename&gt;&#39;이 있으므로 byref 매개 변수와 함께 생성자를 사용하여 특성을 적용할 수 없습니다.
`ByRef` 매개 변수를 사용하는 특성 생성자를 통해 프로그래밍 요소에 특성을 적용했습니다.  
  
 특성은 컴파일 시간에 적용되며, 컴파일러에서 특성 생성자에 전달할 구체적인 값이 필요합니다.`ByRef` 매개 변수가 컴파일 시간에 계산할 수 없는 값에 대한 포인터를 사용합니다.  
  
 `ByRef` 매개 변수를 사용하는 특성 생성자를 정의할 수 있으며, 상속과 같은 용도에 사용할 수 있지만 특성을 적용할 때는 `ByRef` 매개 변수를 사용하지 않는 생성자를 사용해야 합니다.  
  
 **오류 ID:** BC36006  
  
### 이 오류를 해결하려면  
  
-   `ByRef` 매개 변수를 사용하지 않는 생성자를 통해 특성을 적용하거나 특성을 적용하지 마세요.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic의 특성 개요](http://msdn.microsoft.com/ko-kr/0d0cff64-892d-4f57-83bd-bef388553d4f)   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [Passing Arguments by Value and by Reference](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference)   
 [ByRef](/dotnet/visual-basic/language-reference/modifiers/byref)