---
title: "WinCounter | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ff319ffc-f249-4c3f-9eb2-06e392e3ae80
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# WinCounter
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**WinCounter** 옵션은 프로파일링 실행 중 설정된 간격마다 수집할 Windows 또는 응용 프로그램 성능 카운터를 지정합니다.  Windows 및 응용 프로그램 성능 카운터는 프로파일링 데이터 파일에 표시로 나열됩니다.  여러 성능 카운터를 수집하려면 각 카운터를 별개의 옵션에서 지정합니다.  
  
 기본적으로 카운터는 500밀리초마다 수집됩니다.  다른 수집 간격을 지정하려면 **AutoMark** 옵션을 사용합니다.  
  
 **AutoMark** 옵션은 하나만 사용할 수 있습니다.  여러 개의 **AutoMark** 옵션이 지정된 경우 마지막 옵션이 사용됩니다.  
  
 **WinCounter** 옵션은 **Start** 옵션과 함께만 사용할 수 있습니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Start:Method /Wincounter:Path [/WinCounter:Path] [AutoMark:Milliseconds] [Options]  
```  
  
#### 매개 변수  
 `Path`  
 PDH 카운터 경로 형식의 Windows 성능 카운터입니다.  
  
## 필수 옵션  
 **WinCounter** 옵션은 **Start** 옵션과 함께만 사용할 수 있습니다.  
  
 **Start:** `Method`  
 **Start** 옵션은 프로파일러를 지정된 프로파일링 방법으로 초기화합니다.  
  
## 배타적 옵션  
 **AutoMark** 옵션은 **WinCounter** 옵션과 함께만 사용할 수 있습니다.  
  
 **AutoMark:** `Milliseconds`  
 Windows 성능 카운터 데이터가 수집되는 시간 간격\(밀리초\)을 지정합니다.  
  
## 예제  
 다음 예제에서는 1000밀리초 간격으로 두 개의 Windows 성능 카운터를 수집하도록 지정합니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WinCounter:"\Processor(0)\% Processor Time" /WinCounter:"\System\Context Switches/sec" /AutoMark:1000  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)