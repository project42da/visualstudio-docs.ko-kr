---
title: "제네릭 형식 &#39;&lt;generictypename&gt;은 한 번만 가져올 수 있습니다. | Microsoft Docs"
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
  - "BC32086"
  - "vbc32086"
helpviewer_keywords: 
  - "BC32086"
ms.assetid: d93bae4b-3224-4a6e-a072-8ce231084519
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제네릭 형식 &#39;&lt;generictypename&gt;은 한 번만 가져올 수 있습니다.
[Imports Statement \(.NET Namespace and Type\)](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type)에서 다른 형식 매개 변수화를 통해 이미 가져온 제네릭 형식을 지정합니다.  
  
 생성된 형식을 선언하여 제네릭 형식을 재정의하지 않았기 때문에 제네릭 형식에서 생성된 여러 형식을 선언할 수 있습니다. 그러나 제네릭 형식을 두 번 이상 가져오는 경우 정의가 여러 개인 것과 같습니다.  
  
 **오류 ID:** BC32086  
  
### 이 오류를 해결하려면  
  
1.  이 `Imports` 문이 포함된 원본 파일에 동일한 제네릭 형식을 지정하는 다른 `Imports` 문도 포함된 경우 이중 하나를 제거합니다.  
  
2.  다른 형식 매개 변수화를 사용하여 같은 제네릭 형식을 가져와야 하는 경우 여러 원본 파일을 사용합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)