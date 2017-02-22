---
title: "Sys(VSPerfCmd) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 294a6f9e-b49f-4c83-b322-5ac5411b66fb
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Sys(VSPerfCmd)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPerfCmd.exe **Sys** 옵션은 샘플링되는 프로파일링 이벤트를 시스템 호출 이벤트\(프로파일링되는 응용 프로그램에서 운영 체제로의 함수 호출\)로 설정하고, 선택적으로 샘플링 간격의 시스템 호출 수를 기본값인 10에서 다른 값으로 변경합니다.  
  
 **Sys**는 **Launch** 또는 **Attach** 옵션을 함께 포함하는 명령줄에서만 사용할 수 있습니다.  
  
 기본적으로 프로파일러 샘플링 이벤트는 프로세서 클록 주기로 설정되며 샘플링 간격은 10,000,000으로 설정됩니다.  **Timer**, **PF**, **Sys** 및 **Counter** 옵션을 사용하면 샘플링 이벤트와 샘플링 간격을 설정할 수 있습니다.  **GC** 옵션은 각 할당 및 가비지 수집 이벤트에서 .NET 메모리 데이터를 수집합니다.  하나의 명령줄에 이러한 옵션을 하나씩만 지정할 수 있습니다.  
  
 샘플링 이벤트와 샘플링 간격은 **Launch** 또는 **Attach** 옵션이 포함된 첫 번째 명령줄에서만 설정할 수 있습니다.  
  
## 구문  
  
```  
VSPerfCmd.exe {/Launch:AppName|Attach:PID} /Sys[:Events] [Options]  
```  
  
#### 매개 변수  
 `Events`  
 샘플링 간격에서의 시스템 호출 이벤트 수를 지정하는 정수 값입니다.  `Events`를 지정하지 않은 경우 간격은 10으로 설정됩니다.  
  
## 필수 옵션  
 **Sys**를 사용하려면 다음 옵션 중 하나가 필요합니다.  
  
 **Launch:** `AppName`  
 프로파일러와 `AppName`으로 지정된 응용 프로그램을 시작합니다.  
  
 **Attach:** `PID`  
 `PID`로 지정된 프로세스에 프로파일러를 연결합니다.  
  
## 잘못된 옵션  
 다음 옵션은 **Sys**와 같은 명령줄에서 지정할 수 없습니다.  
  
 **PF**\[**:**`Events`\]  
 샘플링 이벤트를 페이지 폴트로 설정하고, 선택적으로 샘플링 간격을 `Events`로 설정합니다.  기본 PF 간격은 10입니다.  
  
 **Timer**\[**:**`Cycles`\]  
 샘플링 이벤트를 프로세서 클록 주기로 설정하고, 선택적으로 샘플링 간격을 `Cycles`로 설정합니다.  기본 타이머 간격은 10,000,000입니다.  
  
 **Counter:** `Name`\[`,Reload`\[`,FriendlyName`\]\]  
 샘플링 이벤트를 `Name`에 지정된 CPU 성능 카운터로 설정하고 샘플링 간격을 `Reload`로 설정합니다.  
  
 **GC**\[**:**{**Allocation**&#124;**Lifetime**}\]  
 .NET 메모리 데이터를 수집합니다.  기본적으로\(**Allocation**\) 데이터는 메모리 할당 이벤트가 발생할 때마다 수집됩니다.  **Lifetime** 매개 변수를 지정하면 각 가비지 수집 이벤트가 발생할 때도 데이터가 수집됩니다.  
  
## 예제  
 이 예제에서는 프로파일러 샘플링 이벤트를 시스템 호출로 설정하고 샘플링 간격을 샘플당 호출 수 20으로 설정하는 방법을 보여 줍니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Sys:20  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)