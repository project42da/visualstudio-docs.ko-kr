---
title: "대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다. | Microsoft Docs"
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
  - "vbrIO_CyclicOperation"
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.
순환 작업이 실패했습니다. 순환 작업이 계속 실행되므로 완료할 수 없습니다. 예를 들어 개체 A는 개체 B에서 상속하려고 하고 개체 B는 개체 A에서 상속하려고 합니다.  
  
### 이 오류를 해결하려면  
  
-   상속 시 순환 참조가 없어야 합니다.  
  
## 참고 항목  
 [Error Types](/dotnet/visual-basic/programming-guide/language-features/error-types)   
 [Debugging Basics: Breakpoints](http://msdn.microsoft.com/ko-kr/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)