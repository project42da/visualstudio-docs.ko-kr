---
title: "Shutdown | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Shutdown
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**Shutdown** 옵션은 현재 프로파일링되는 프로세스가 종료되거나 분리될 때까지 기다렸다가 프로파일러를 해제하고 프로파일링 데이터 파일을 닫습니다.  **Shutdown** 옵션은 프로파일링 실행의 마지막 명령이어야 합니다.  
  
 시간 제한 매개 변수를 지정하지 않을 경우 **Shutdown** 옵션은 무기한 대기합니다.  시간 제한 매개 변수를 지정하면 이 옵션은 프로파일러를 해제하거나 데이터 파일을 닫지 않고 지정한 시간\(초\)이 지나면 반환됩니다.  
  
 **Shutdown** 옵션은 명령줄에서 단독으로 지정해야 합니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### 매개 변수  
 `Timeout`  
 -   선택적 요소로, 이 매개 변수를 지정할 경우 이 옵션은 프로파일러를 해제하거나 프로파일링 데이터 파일을 닫지 않고 지정한 시간\(초\)이 지나면 반환됩니다.  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)