---
title: "구현된 형식이 인터페이스여야 합니다. | Microsoft Docs"
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
  - "bc30232"
  - "vbc30232"
helpviewer_keywords: 
  - "BC30232"
ms.assetid: 63f3dd4c-2f99-4070-b506-2fa808df24d4
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 구현된 형식이 인터페이스여야 합니다.
`Implements` 문이 인터페이스를 지정하지 않습니다. 각 클래스가 하나의 인터페이스만 구현할 수 있습니다.  
  
 **오류 ID:** BC30232  
  
### 이 오류를 해결하려면  
  
1.  인터페이스 이름의 철자가 맞는지 확인합니다.  
  
2.  문이 클래스를 지정하는 경우 `Inherits` 문을 사용하는 것이 좋습니다.  
  
## 참고 항목  
 [Implements Statement](/dotnet/visual-basic/language-reference/statements/implements-statement)   
 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)   
 [빌드에 없음: Visual Basic의 상속](http://msdn.microsoft.com/ko-kr/e5e6e240-ed31-4657-820c-079b7c79313c)