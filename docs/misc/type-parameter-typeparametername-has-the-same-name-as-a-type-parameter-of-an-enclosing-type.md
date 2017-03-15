---
title: "&#39;&lt;typeparametername&gt;&#39; 형식 매개 변수의 이름이 바깥쪽 형식의 형식 매개 변수와 같습니다. | Microsoft Docs"
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
  - "vbc40048"
  - "bc40048"
helpviewer_keywords: 
  - "BC40048"
ms.assetid: d5428b36-88d3-42c4-a096-cbc7bb9571f2
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typeparametername&gt;&#39; 형식 매개 변수의 이름이 바깥쪽 형식의 형식 매개 변수와 같습니다.
제네릭 형식의 형식 매개 변수가 포함하는 제네릭 형식의 형식 매개 변수와 같은 이름으로 선언됩니다.  
  
 제네릭 형식의 형식 매개 변수 목록에서 각 형식 매개 변수 이름은 다음 이름과 모두 구별되어야 합니다.  
  
-   동일한 형식 매개 변수 목록에 있는 다른 모든 형식 매개 변수  
  
-   포함하는 제네릭 형식의 형식 매개 변수 목록에 있는 모든 형식 매개 변수  
  
-   제네릭 형식 자체의 이름입니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40048  
  
### 이 오류를 해결하려면  
  
-   이 도움말 페이지의 목록에 명시된 모든 이름과 구별되도록 형식 매개 변수의 이름을 바꿉니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)