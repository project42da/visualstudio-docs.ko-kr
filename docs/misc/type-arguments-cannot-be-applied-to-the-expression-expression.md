---
title: "형식 인수는 &#39;&lt;expression&gt;&#39; 식에 적용할 수 없습니다. | Microsoft Docs"
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
  - "bc32058"
  - "vbc32058"
helpviewer_keywords: 
  - "BC32058"
ms.assetid: c6b9b49c-6fb2-47b8-a8bb-464562d3adfd
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 인수는 &#39;&lt;expression&gt;&#39; 식에 적용할 수 없습니다.
가져오기 별칭에 형식 인수를 전달하는 [Of](/dotnet/visual-basic/language-reference/statements/of-clause) 절을 사용하여 가져오기 별칭이 정의되었습니다.  
  
 형식 인수는 제네릭 형식에 사용되며 클래스, 구조체, 인터페이스, 프로시저 및 대리자만 제네릭일 수 있습니다. 네임스페이스와 가져오기 별칭은 제네릭이 될 수 없습니다.  
  
 **오류 ID:** BC32058  
  
### 이 오류를 해결하려면  
  
-   가져오기 별칭에서 `Of` 절과 해당 형식 인수를 제거합니다.  
  
## 참고 항목  
 [Imports Statement \(.NET Namespace and Type\)](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type)   
 [References and the Imports Statement](/dotnet/visual-basic/programming-guide/program-structure/references-and-the-imports-statement)   
 [NOTINBUILD: 여러 변수에 동일한 이름이 있는 경우 참조 확인](http://msdn.microsoft.com/ko-kr/9601e39f-1911-44e1-ace5-3f6e090408b9)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)