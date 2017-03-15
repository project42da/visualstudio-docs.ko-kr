---
title: "&#39;&lt;specifier&gt;&#39;는 인터페이스 메서드 선언에서 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30270"
  - "vbc30270"
helpviewer_keywords: 
  - "BC30270"
ms.assetid: 598f2944-3e5d-4686-b6f7-2b4bcaf5c211
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;specifier&gt;&#39;는 인터페이스 메서드 선언에서 사용할 수 없습니다.
인터페이스 내의 `Function` 또는 `Sub` 문에 `Implements`와 같은 잘못된 키워드가 포함되어 있습니다. 인터페이스는 멤버를 정의할 수만 있고 구현할 수는 없습니다.  
  
 **오류 ID:** BC30270  
  
### 이 오류를 해결하려면  
  
1.  선언문에서 잘못된 키워드를 제거합니다.  
  
2.  인터페이스 멤버의 구현을 해당 인터페이스를 구현하는 클래스로 이동합니다.  
  
## 참고 항목  
 [Interface Statement](/dotnet/visual-basic/language-reference/statements/interface-statement)   
 [Implements Statement](/dotnet/visual-basic/language-reference/statements/implements-statement)