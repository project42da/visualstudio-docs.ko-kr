---
title: "형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;은 자신의 제약을 받을 수 없습니다. &#39;&lt;errormessage&gt;&#39; | Microsoft Docs"
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
  - "bc32113"
  - "vbc32113"
helpviewer_keywords: 
  - "BC32113"
ms.assetid: a74128ae-11d0-46bf-8c0b-c7a2bf881d17
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;은 자신의 제약을 받을 수 없습니다. &#39;&lt;errormessage&gt;&#39;
형식 매개 변수에 대한 제약 조건 목록에 동일한 형식 매개 변수가 포함됩니다.  
  
 형식 매개 변수의 제약 조건 목록에 지정할 수 있는 인터페이스 수에는 제한이 없으며 클래스는 최대 하나만 지정할 수 있습니다. 해당 형식 매개 변수에 대해 제공된 형식 인수는 지정된 모든 인터페이스를 구현해야 하며 지정된 클래스에서 상속해야 합니다. 컴파일러에는 제약 조건 목록이 생성될 때 이미 정의된 인터페이스 및 클래스가 필요합니다. 형식 매개 변수는 제네릭 형식을 생성하는 코드에서 제공된 적합한 형식 인수로 대체될 때까지 정의된 형식으로 간주되지 않습니다.  
  
 **오류 ID:** BC32113  
  
### 이 오류를 해결하려면  
  
1.  형식 매개 변수와 제약 조건 목록의 제약 조건의 철자를 확인합니다.  
  
2.  철자 오류가 없는 경우 형식 매개 변수의 이름을 해당 제약 조건 목록에서 제거합니다. 형식 매개 변수는 자신의 제약을 받을 수 없습니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)