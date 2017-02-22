---
title: "콘솔 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e825ba66-1383-46ad-8712-396bc9c14036
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 콘솔
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPerfCmd.exe **Console** 옵션은 새 명령 프롬프트 창에서 지정된 응용 프로그램을 시작합니다.  **Console**은 VSPerfCmd **Launch** 옵션과 함께만 사용할 수 있습니다.  지정된 응용 프로그램이 명령줄 응용 프로그램이 아닌 경우 **Console**은 아무런 영향을 주지 않습니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Launch:AppName /Console  
```  
  
#### 매개 변수  
 없음  
  
## 필수 옵션  
 **Console**은 **Launch** 옵션이 포함된 명령줄에서만 지정할 수 있습니다.  
  
 **Launch:** `AppName`  
 프로파일러와 `AppName`으로 지정된 응용 프로그램을 시작합니다.  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)