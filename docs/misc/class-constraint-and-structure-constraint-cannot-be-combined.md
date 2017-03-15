---
title: "&#39;Class&#39; 제약 조건과 &#39;Structure&#39; 제약 조건은 함께 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc32104"
  - "bc32104"
helpviewer_keywords: 
  - "BC32104"
ms.assetid: f41a581b-afca-4173-bc82-b35ed49caba0
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Class&#39; 제약 조건과 &#39;Structure&#39; 제약 조건은 함께 사용할 수 없습니다.
제약 조건 목록에는 [클래스\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/0777c6e6-46bc-451b-ad70-57b49d4ef4f7) 제약 조건 및 [구조체\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/263ce115-ac36-4c05-8cb7-0e0eead5c6d0) 제약 조건이 모두 포함됩니다.  
  
 형식 매개 변수의 제약 조건 목록은 해당 형식 매개 변수에 전달된 형식 인수가 값 형식\(`Structure` 제약 조건 사용\)이 되거나 참조 형식\(`Class` 제약 조건 사용\)이 되도록 지정할 수 있습니다. 동일한 형식 매개 변수에 제약 조건을 둘 다 지정할 수 없으며 두 번 이상 지정할 수도 없습니다.  
  
 **오류 ID:** BC32104  
  
### 이 오류를 해결하려면  
  
1.  형식 인수를 값 형식으로 할 것인지 또는 참조 형식으로 할 것인지 결정합니다.  
  
    -   형식 인수를 값 형식으로 하려면 제약 조건 목록에서 `Class` 키워드를 제거합니다.  
  
    -   형식 인수를 참조 형식으로 하려면 제약 조건 목록에서 `Structure` 키워드를 제거합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Value Types and Reference Types](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)