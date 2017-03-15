---
title: "구조체의 메서드 내에 있는 지역 변수는 &#39;Static&#39;으로 선언할 수 없습니다. | Microsoft Docs"
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
  - "vbc31400"
  - "bc31400"
helpviewer_keywords: 
  - "BC31400"
ms.assetid: 38b8adee-3593-40fb-b0a4-e2a47599567f
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 구조체의 메서드 내에 있는 지역 변수는 &#39;Static&#39;으로 선언할 수 없습니다.
`Static` 한정자는 구조체에서 지역 변수와 함께 사용할 수 없습니다.  
  
 **오류 ID:** BC31400  
  
### 이 오류를 해결하려면  
  
1.  지역 변수에서 `Static` 한정자를 제거합니다.  
  
2.  변수를 보다 넓은 범위의 정적 변수로 선언합니다.  
  
## 참고 항목  
 [Static](/dotnet/visual-basic/language-reference/modifiers/static)