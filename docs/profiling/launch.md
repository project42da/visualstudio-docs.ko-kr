---
title: "시작 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f81bde5c-3394-4b79-a315-c2f6491689b3
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 시작
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**Launch** 옵션은 샘플링 방법을 사용하여 프로파일러를 시작하고 지정된 응용 프로그램도 시작합니다.  
  
 **Launch** 옵션을 사용하려면 **Start** 옵션에서 **Sample** 메서드를 지정해야 합니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Launch:AppName [Options]  
```  
  
#### 매개 변수  
 `AppName`  
 시작할 응용 프로그램의 이름입니다.  현재 디렉터리부터의 부분 경로나 전체 경로를 사용할 수 있습니다.  
  
## 유효한 옵션  
 다음 VSPerfCmd 옵션은 단일 명령줄에서 **Launch** 옵션과 함께 사용할 수 있습니다.  
  
 **Start:** `Method`  
 명령줄 프로파일러 세션을 초기화하고 지정된 프로파일링 방법을 설정합니다.  
  
 **GlobalOn**and**GlobalOff**  
 프로파일링을 다시 시작\(**GlobalOn**\)하거나 일시 중지\(**GlobalOff**\)하지만 프로파일링 세션을 종료하지는 않습니다.  
  
 **ProcessOn:** `PID` 및 **ProcessOff**:`PID`  
 지정된 프로세스에 대한 프로파일링을 다시 시작\(**ProcessOn**\)하거나 일시 중지 \(**ProcessOff**\)합니다.  
  
 **TargetCLR**  
 프로파일링 세션에 둘 이상의 .NET Framework CLR\(공용 언어 런타임\) 버전이 로드될 때 프로파일링할 버전을 지정합니다.  기본적으로는 첫 번째로 로드되는 버전이 프로파일링됩니다.  
  
## 배타적 옵션  
 다음 옵션은 **Launch** 옵션과 함께만 사용할 수 있습니다.  
  
 **Console**  
 지정된 명령줄 응용 프로그램을 새 창에서 시작합니다.  
  
 **Args:** `ArgList`  
 응용 프로그램에 전달할 인수 목록을 지정합니다.  
  
 **LineOff**  
 줄 수준 프로파일링 데이터의 수집을 사용하지 않습니다.  
  
## 샘플링 옵션  
 다음 샘플링 간격 옵션 중 하나를 **Launch** 명령줄에서 지정할 수 있습니다.  기본 샘플링 간격은 10,000,000개의 프로세서 클록 주기입니다.  
  
 **Timer**\[**:**`Cycles`\]**PF**\[**:**`Events`\]**Sys**\[**:**`Events`\]**Counter**\[**:**`Name`,`Reload`,`FriendlyName`\]**GC**\[:**allocation**&#124;**lifetime**\]  
 샘플링 간격의 수와 형식을 지정합니다.  
  
-   **Timer** \- 중단되지 않은 프로세서 클록 주기가 `Cycles`로 지정한 개수가 될 때마다 샘플링합니다.  `Cycles`가 지정되지 않은 경우 10,000,000개의 주기가 사용됩니다.  
  
-   **PF** \- 페이지 폴트가 `Events`로 지정한 개수가 될 때마다 샘플링합니다.  `Events`가 지정되지 않은 경우 10개의 페이지 폴트가 사용됩니다.  
  
-   **Sys** \- 운영 체제에 대한 호출이 `Events`로 지정한 개수가 될 때마다 샘플링합니다.  `Events`가 지정되지 않은 경우 10개의 시스템 호출이 사용됩니다.  
  
-   **Counter** \- `Name`으로 지정한 CPU 성능 카운터가 `Reload`로 지정한 개수가 될 때마다 샘플링합니다.  필요한 경우 `FriendlyName`을 통해 프로파일러 보고서의 열 머리글로 사용할 문자열을 지정할 수 있습니다.  
  
-   **GC** \- .NET 메모리 데이터를 수집합니다.  기본적으로\(**allocation**\) 데이터는 메모리 할당 이벤트가 발생할 때마다 수집됩니다.  **lifetime** 매개 변수를 지정하면 각 가비지 수집 이벤트가 발생할 때도 데이터가 수집됩니다.  
  
## 예제  
 이 예제에서는 **Launch**를 사용하여 응용 프로그램을 시작하는 방법을 보여 줍니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)