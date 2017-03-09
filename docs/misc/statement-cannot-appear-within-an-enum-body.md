---
title: "Enum 본문 안에는 문을 사용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30619"
  - "bc30619"
helpviewer_keywords: 
  - "BC30619"
ms.assetid: 5d91d601-2a2d-418c-ae26-791d14a6f3cd
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Enum 본문 안에는 문을 사용할 수 없습니다.
Enum 본문 안에는 문을 사용할 수 없습니다. 열거형의 끝으로 간주합니다.  
  
 예기치 않은 언어 구문이 발견되었습니다.`End Enum` 구문이 누락되었고 이 포인트 다음에 나오는 소스 코드는 열거형 바깥에 있다고 가정합니다.  
  
 **오류 ID:** BC30619  
  
### 이 오류를 해결하려면  
  
1.  열거형 내부에서 사용되는 코드의 구문을 확인합니다.  
  
2.  인터페이스 정의가 `End Enum` 구문으로 끝나는지 확인합니다.  
  
## 참고 항목  
 [Enum Statement](/dotnet/visual-basic/language-reference/statements/enum-statement)