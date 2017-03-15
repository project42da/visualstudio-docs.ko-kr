---
title: "&#39;&lt;qualifiedelementname&gt;&#39;에 대한 Imports 별칭의 &#39;&lt;elementname&gt;&#39;은 Namespace, Class, Structure, Interface, Enum 또는 Module을 참조하지 않습니다. | Microsoft Docs"
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
  - "bc30798"
  - "vbc30798"
helpviewer_keywords: 
  - "BC30798"
ms.assetid: bfa66627-516a-4955-977d-92372bcea090
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;qualifiedelementname&gt;&#39;에 대한 Imports 별칭의 &#39;&lt;elementname&gt;&#39;은 Namespace, Class, Structure, Interface, Enum 또는 Module을 참조하지 않습니다.
[Imports Statement \(.NET Namespace and Type\)](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type)은 가져올 수 없는 프로그래밍 요소를 지정합니다.  
  
 `Imports` 문은 요소 이름 앞에 오는 한정 문자열에 대한 요구 사항을 줄이거나 제거하는 데 사용합니다.`Imports` 문 자체에서 요소를 한정하여 고유한 요소 선언에 대한 명확한 경로를 제공합니다. 그런 다음 요소에 대한 참조를 한정할 필요가 없습니다.  
  
 네임스페이스에 `Imports`가 가장 일반적으로 사용되지만 클래스, 모듈, 구조체, 인터페이스 또는 열거형을 가져와서 긴 한정 문자열이 없는 해당 요소에 대한 참조를 허용할 수도 있습니다.  
  
 자세한 내용은 [NOTINBUILD: 여러 변수에 동일한 이름이 있는 경우 참조 확인](http://msdn.microsoft.com/ko-kr/9601e39f-1911-44e1-ace5-3f6e090408b9)에서 "포함하는 요소 가져오기"를 참조하세요.  
  
 **오류 ID:** BC30798  
  
### 이 오류를 해결하려면  
  
1.  `Imports` 문의 한정 문자열에서, 특히 한정하는 요소인 문자열의 마지막 요소의 철자를 확인합니다.  
  
2.  한정하는 요소가 적합한 형식\(네임스페이스, 클래스, 모듈, 구조체, 인터페이스 또는 열거형\)인지 확인합니다. 적합한 형식이 아닌 경우 `Imports` 문을 제거합니다.  
  
## 참고 항목  
 [References and the Imports Statement](/dotnet/visual-basic/programming-guide/program-structure/references-and-the-imports-statement)