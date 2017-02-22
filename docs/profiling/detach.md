---
title: "Detach | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9d1b52c-7f28-467d-b1e0-512afc4e46c9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Detach
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPerfCmd.exe **Detach** 옵션은 지정된 프로세스나 모든 프로세스\(프로세스가 지정되지 않은 경우\)에서 프로파일러의 연결을 끊습니다.  이때 프로파일링은 샘플링 방법을 사용하여 초기화되었어야 합니다.  
  
 **Launch** 또는 **Attach** 옵션 중 하나를 사용하여 시작된 프로파일링은 **Detach**를 사용하여 연결을 끊을 수 있습니다.  이후에 **Attach** 명령을 사용하면 프로파일러를 다시 연결할 수 있습니다.  
  
 **Detach**는 프로파일링 데이터 파일을 닫지 않습니다.  프로파일링을 종료하고 데이터 파일을 닫으려면 **Shutdown** 옵션을 사용합니다.  
  
> [!NOTE]
>  **Start** 옵션을 **Crosssession** 옵션과 함께 지정한 경우 **VSPerfCmd \/Attach** 또는 **VSPerfCmd \/Detach**에 대한 모든 호출에서도 **Crosssession**을 지정해야 합니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Detach[:PIDs|ProcessNames]  
```  
  
#### 매개 변수  
 `PIDs|ProcessNames`  
 `PID` \- 하나 이상의 프로세스에 대한 숫자로 된 시스템 식별자입니다.  
  
 `ProcessNames` \- 프로세스의 이름입니다.  지정된 프로세스의 인스턴스가 여러 개 실행되고 있는 경우에는 결과를 예측할 수 없습니다.  
  
 프로세스를 여러 개 지정할 때는 각 프로세스를 쉼표로 구분합니다.  
  
 프로세스를 지정하지 않으면 프로파일링되는 모든 프로세스에서 프로파일러가 분리됩니다.  
  
## 유효한 옵션  
 다음 **VSPerfCmd** 옵션은 단일 명령줄에서 **Attach** 옵션과 함께 사용할 수 있습니다.  
  
 **Crosssession**  
 로그온 세션 이외의 세션에서 응용 프로그램을 프로파일링할 수 있도록 합니다.  **Start** 옵션을 **Crosssession** 옵션과 함께 지정한 경우 필수적 요소입니다.  
  
## 예제  
 이 예제에서 **Detach** 명령은 프로파일링을 일시 중지하고 **Shutdown** 명령은 프로파일러 데이터 파일을 닫습니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
;REM Excercise the application  
VSPerfCmd.exe /Detach  
VSPerfCmd.exe /Shutdown  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)