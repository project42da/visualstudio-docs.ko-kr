---
title: "인터페이스 본문 안에는 문을 사용할 수 없습니다(Visual Basic 오류). | Microsoft Docs"
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
  - "bc30604"
  - "vbc30604"
helpviewer_keywords: 
  - "BC30604"
ms.assetid: ce4759fe-5e49-43ad-8405-a3f46ed0a36f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 인터페이스 본문 안에는 문을 사용할 수 없습니다(Visual Basic 오류).
예기치 않은 언어 구문이 발견되었습니다.`End Interface` 구문이 누락되었고 이 지점 다음에 나오는 소스 코드는 인터페이스 바깥쪽에 있다고 가정합니다.  
  
 **오류 ID:** BC30604  
  
### 이 오류를 해결하려면  
  
1.  인터페이스 정의 내부에서 사용되는 코드의 구문을 확인합니다.  
  
2.  인터페이스 정의가 `End Interface` 구문으로 끝나는지 확인합니다.  
  
## 참고 항목  
 [Interfaces](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)   
 [Interface Statement](/dotnet/visual-basic/language-reference/statements/interface-statement)