---
title: "&#39;New&#39; 제약 조건과 &#39;Structure&#39; 제약 조건은 함께 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc32103"
  - "vbc32103"
helpviewer_keywords: 
  - "BC32103"
ms.assetid: 5418b420-a014-4006-84aa-20ddac6739e6
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;New&#39; 제약 조건과 &#39;Structure&#39; 제약 조건은 함께 사용할 수 없습니다.
제약 조건 목록에는 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator) 제약 조건 및 [구조체\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/263ce115-ac36-4c05-8cb7-0e0eead5c6d0) 제약 조건이 모두 포함됩니다.  
  
 형식 매개 변수의 제약 조건 목록은 해당 형식 매개 변수에 전달된 형식 인수가 값 형식\(`Structure` 제약 조건 사용\)이 되거나 참조 형식\([클래스\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/0777c6e6-46bc-451b-ad70-57b49d4ef4f7) 제약 조건 사용\)이 되도록 지정할 수 있습니다. 동일한 형식 매개 변수에 제약 조건을 둘 다 지정할 수 없으며 두 번 이상 지정할 수도 없습니다.  
  
 `New` 제약 조건은 해당 형식 인수에서 만드는 코드가 액세스할 수 있는, 매개 변수 없는 생성자를 노출해야 한다는 것을 지정합니다. 그러나 구조체는 공유되지 않는 매개 변수가 없는 생성자를 가질 수 없습니다. 따라서 `New` 및 `Structure` 제약 조건이 서로 충돌합니다.  
  
 **오류 ID:** BC32103  
  
### 이 오류를 해결하려면  
  
1.  형식 인수를 값 형식으로 할 것인지 또는 참조 형식으로 할 것인지 결정합니다.  
  
2.  형식 인수를 값 형식으로 하려면 제약 조건 목록에서 `New` 키워드를 제거합니다.  
  
3.  형식 인수를 참조 형식으로 하려면 제약 조건 목록에서 `Structure` 키워드를 제거합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Value Types and Reference Types](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)