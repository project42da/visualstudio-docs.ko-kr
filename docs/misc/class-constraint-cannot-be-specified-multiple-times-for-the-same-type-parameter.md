---
title: "동일한 형식 매개 변수에는 ‘Class’ 제약 조건을 여러 번 지정할 수 없습니다. | Microsoft Docs"
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
  - "bc32101"
  - "vbc32101"
helpviewer_keywords: 
  - "BC32101"
ms.assetid: fac2330a-e397-4bd9-8166-934407575f9e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 동일한 형식 매개 변수에는 ‘Class’ 제약 조건을 여러 번 지정할 수 없습니다.
제약 조건 목록에는 [클래스\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/0777c6e6-46bc-451b-ad70-57b49d4ef4f7) 제약 조건이 두 번 이상 포함되어 있습니다.  
  
 형식 매개 변수의 제약 조건 목록은 해당 형식 매개 변수에 전달된 형식 인수가 값 형식\([구조체\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/263ce115-ac36-4c05-8cb7-0e0eead5c6d0) 제약 조건 사용\)이 되거나 참조 형식\(`Class` 제약 조건 사용\)이 되도록 지정할 수 있습니다. 동일한 형식 매개 변수에 제약 조건을 둘 다 지정할 수 없으며 두 번 이상 지정할 수도 없습니다.  
  
 오류 ID: BC32101  
  
### 이 오류를 해결하려면  
  
-   중복된 `Class` 키워드를 모두 제거합니다. 제약 조건 목록에 하나만 있어야 합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Value Types and Reference Types](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)