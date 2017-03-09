---
title: "형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;은 클래스 제약 조건을 하나만 가질 수 있습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32047"
  - "vbc32047"
helpviewer_keywords: 
  - "BC32047"
ms.assetid: ac7ab76b-5300-4c79-b519-5a1287ed5fa9
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;은 클래스 제약 조건을 하나만 가질 수 있습니다.
제약 조건 목록에는 둘 이상의 클래스가 있습니다.  
  
 형식 매개 변수의 제약 조건 목록에 수용할 수 있는 인터페이스 수는 제한이 없지만 클래스는 최대 하나만 수용할 수 있습니다. 해당 형식 매개 변수에 제공되는 형식 인수는 해당 클래스에서 상속해야 하며 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]는 다중 상속을 지원하지 않습니다.  
  
 **오류 ID:** BC32047  
  
### 이 오류를 해결하려면  
  
-   하나의 클래스를 선택하고 제약 조건 목록에서 해당 클래스만 포함합니다.  
  
-   이 제약 조건 목록에 포함할 수 없는 클래스를 수용하기 위해 추가 형식 매개 변수를 정의할 수도 있습니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)