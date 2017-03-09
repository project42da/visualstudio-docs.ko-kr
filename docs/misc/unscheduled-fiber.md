---
title: "예약되지 않은 파이버입니다. | Microsoft Docs"
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
  - "bc30948"
  - "vbc30948"
helpviewer_keywords: 
  - "BC30948"
ms.assetid: 982bf6d2-ce62-4451-8a23-82dacf8ee100
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 예약되지 않은 파이버입니다.
실제 스레드에 예약되지 않은 논리 파이버에 있기 때문에 디버거에서 식을 계산할 수 없습니다. 이 오류는 프로세스가 파이버를 사용하여 SQL Server에서 실행 중인 경우에 발생할 수 있습니다.  
  
 파이버는 스택 및 레지스터 컨텍스트로 구성되며, 모든 스레드에서 실행할 수 있습니다. 파이버는 스레드에서 교환하여 나중에 다른 스레드에서 다시 시작할 수 있습니다.  
  
 **오류 ID:** BC30948  
  
### 이 오류를 해결하려면  
  
-   파이버가 실제 스레드에 예약되어 있는지 확인합니다.  
  
## 참고 항목  
 [Debugging SQL](http://msdn.microsoft.com/ko-kr/f27c17e6-1d90-49f2-9fc0-d02e6a27f109)   
 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)