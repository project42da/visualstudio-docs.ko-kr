---
title: "AutoMark | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# AutoMark
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**AutoMark** 옵션은 Windows 소프트웨어 성능 카운터 이벤트의 수집 간격을 밀리초 단위로 지정합니다.  Windows 성능 카운터는 **WinCounter** 옵션에서 지정합니다.  
  
 **AutoMark** 옵션은 명령줄에서 하나만 지정할 수 있습니다.  **AutoMark**로 지정된 **WinCounter** 샘플링 간격은 주 샘플링 간격과는 상관이 없습니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds  
```  
  
#### 매개 변수  
 `Milliseconds`  
 Windows 성능 카운터 이벤트의 수집 간격\(밀리초\)을 지정합니다.  
  
## 필수 옵션  
 **WinCounter:** `Path`  
 수집할 Windows 성능 카운터를 지정합니다.  계측 방법을 사용할 때는 Windows 카운터를 여러 개 지정할 수 있습니다.  샘플링 방법을 사용할 때는 소프트웨어 카운터 하나만 지정할 수 있습니다.  **WinCounter** 옵션은 **Start** 옵션이 포함된 명령줄에서 지정해야 합니다.  
  
## 예제  
 이 예제에서는 두 개의 Windows 성능 카운터에 대해 샘플링 간격이 1000밀리초로 설정됩니다.  
  
```  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)