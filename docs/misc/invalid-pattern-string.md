---
title: "잘못된 패턴 문자열 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 잘못된 패턴 문자열
검색의 `Like` 작업에서 지정된 패턴 문자열이 잘못되었습니다.  
  
### 이 오류를 해결하려면  
  
1.  목록 식에 유효한 문자를 검토합니다.  
  
2.  패턴 범위에서 `[a-z]`처럼 범위 시작 문자가 범위 끝 문자보다 작은지 확인합니다.  
  
3.  패턴 범위에서 `[a--z]`처럼 여러 하이픈이 서로 인접하지 않는지 확인합니다.  
  
4.  닫는 대괄호를 사용하여 패턴 범위를 종료합니다.  
  
## 참고 항목  
 [Like Operator](/dotnet/visual-basic/language-reference/operators/like-operator)