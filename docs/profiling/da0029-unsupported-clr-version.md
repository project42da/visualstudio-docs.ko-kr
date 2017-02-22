---
title: "DA0029: 지원되지 않는 CLR 버전 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.29"
  - "vs.performance.rules.DA0029"
helpviewer_keywords: 
  - "vs.performance.29"
  - "vs.performance.DA0029"
  - "vs.performance.rules.DA0029"
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0029: 지원되지 않는 CLR 버전
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0029|  
|범주|프로파일링 도구 사용|  
|프로파일링 방법|명령줄에서 프로파일링|  
|메시지|수집하는 동안 지원되지 않는 CLR 버전이 검색되었습니다.  관리되는 기호가 제대로 확인되지 않은 것 같습니다.|  
|규칙 유형|정보|  
  
## 원인  
 프로파일링 도구에서 지원되지 않는 [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)]을 사용하는 응용 프로그램을 프로파일링하려고 했습니다.  
  
## 규칙 설명  
 이 경고는 프로파일링 도구가 응용 프로그램에서 실행되는 관리 코드의 기호를 확인할 수 없기 때문에 발생합니다.  프로파일링 도구에서는 [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)]을 실행하는 응용 프로그램의 관리 코드 기호를 확인할 수 없습니다.  
  
## 위반 문제를 해결하는 방법  
 없음