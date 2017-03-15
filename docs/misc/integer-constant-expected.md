---
title: "정수 상수가 필요합니다. | Microsoft Docs"
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
  - "bc30204"
  - "vbc30204"
helpviewer_keywords: 
  - "BC30204"
ms.assetid: e8d2fe24-7e63-4c30-b022-3b0323f00f4e
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 정수 상수가 필요합니다.
`#ExternalSource` 지시문은 두 번째 인수가 정수 리터럴이 아닌 컨텍스트에서 발생합니다. 정수 리터럴만 이 컨텍스트에서 유효합니다. 명명된 상수 또는 열거형 멤버는 유효하지 않습니다.  
  
 **오류 ID:** BC30204  
  
### 이 오류를 해결하려면  
  
1.  리터럴 대신 명명된 상수 또는 열거형 멤버를 사용합니다.  
  
2.  정수 리터럴을 두 번째 인수로 `#ExternalSource` 지시문에 제공합니다.  
  
## 참고 항목  
 [\#ExternalSource Directive](/dotnet/visual-basic/language-reference/directives/externalsource-directive)