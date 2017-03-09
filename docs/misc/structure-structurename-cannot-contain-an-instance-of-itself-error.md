---
title: "&#39;&lt;structurename&gt;&#39; 구조체는 자체 인스턴스를 포함할 수 없습니다. &lt;error&gt; | Microsoft Docs"
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
  - "vbc30294"
  - "bc30294"
helpviewer_keywords: 
  - "BC30294"
ms.assetid: 17780e11-2425-4860-9345-b5db019d2bf3
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;structurename&gt;&#39; 구조체는 자체 인스턴스를 포함할 수 없습니다. &lt;error&gt;
구조체는 변수를 선언하고 자체 인스턴스를 사용하여 초기화합니다.  
  
 구조체에 다른 구조체의 인스턴스를 포함할 수 있지만 자체의 내부 인스턴스를 포함할 수는 없습니다. 이렇게 하려고 하면 무한 재귀가 발생합니다.  
  
 **오류 ID:** BC30294  
  
### 이 오류를 해결하려면  
  
1.  선언 문에서 초기화 식의 철자를 확인합니다.  
  
2.  동일한 구조체의 다른 인스턴스를 만들려는 경우 구조체 밖에서 선언하고 만들어야 합니다.  
  
## 참고 항목  
 [Structures](/dotnet/visual-basic/programming-guide/language-features/data-types/structures)   
 [Structure Statement](/dotnet/visual-basic/language-reference/statements/structure-statement)