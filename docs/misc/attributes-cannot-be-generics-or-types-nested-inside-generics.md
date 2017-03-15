---
title: "특성은 제네릭 또는 제네릭 내에서 중첩된 형식일 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32067"
  - "vbc32067"
helpviewer_keywords: 
  - "BC32067"
ms.assetid: 93ae2848-0a72-4ae5-82a3-32e0a49bb7cd
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 특성은 제네릭 또는 제네릭 내에서 중첩된 형식일 수 없습니다.
특성이 제네릭 형식으로 또는 제네릭 형식 내에서 선언되었습니다.  
  
 Visual Basic 및 .NET Framework는 현재 특성과 제네릭 형식의 조합을 지원하지 않습니다. 즉, 다음 제한 사항이 적용됩니다.  
  
-   특성은 제네릭 형식이거나 제네릭 형식 내에서 선언될 수 없습니다.  
  
-   특성이 제네릭 클래스에서 상속할 수 없고 제네릭 클래스를 특성에서 상속할 수도 없습니다.  
  
-   특성을 적용하는 경우 다음 중 하나에 해당하는 인수를 제공할 수 없습니다.  
  
    -   제네릭 형식,  
  
    -   제네릭 형식에서 생성되는 형식,  
  
    -   포함 형식의 형식 매개 변수 또는  
  
    -   포함 형식의 형식 매개 변수에서 생성되는 형식  
  
 **오류 ID:** BC32067  
  
### 이 오류를 해결하려면  
  
-   특성 선언에 `Of` 키워드 및 형식 매개 변수 목록이 포함된 경우 제거합니다.  
  
-   특성 선언이 제네릭 형식 안에 표시되는 경우 제네릭 형식 안이 아닌 위치로 이동합니다.  
  
## 참고 항목  
 <xref:System.Attribute>   
 [빌드에 없음: Visual Basic의 특성 개요](http://msdn.microsoft.com/ko-kr/0d0cff64-892d-4f57-83bd-bef388553d4f)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)