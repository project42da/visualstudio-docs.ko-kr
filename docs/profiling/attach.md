---
title: "연결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 79614283-6733-4592-a53a-d428052271ad
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 연결
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPerfCmd.exe **Attach** 옵션은 PID\(프로세스 ID\)로 지정된 실행 중인 프로세스의 샘플 프로파일링을 시작합니다.  
  
 **Attach** 옵션을 사용하려면 Start 옵션에서 **Sample** 메서드를 지정해야 합니다.  
  
> [!NOTE]
>  **Start** 옵션을 **Crosssession** 옵션과 함께 지정한 경우 **VSPerfCmd \/Attach** 또는 **VSPerfCmd \/Detach**에 대한 모든 호출에서도 **Crosssession**을 지정해야 합니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Attach:ProcessID [Options]  
```  
  
#### 매개 변수  
 `ProcessID`  
 실행 중인 프로세스의 PID\(프로세스 ID\)입니다.  실행 중인 프로세스의 PID는 Windows 작업 관리자의 프로세스 탭에 표시됩니다.  
  
## 유효한 옵션  
 다음 **VSPerfCmd** 옵션은 단일 명령줄에서 **Attach** 옵션과 함께 사용할 수 있습니다.  
  
 **Crosssession**  
 로그온 세션 이외의 세션에서 응용 프로그램을 프로파일링할 수 있도록 합니다.  **Start** 옵션을 **Crosssession** 옵션과 함께 지정한 경우 필수적 요소입니다.  
  
 **Start:** `Method`  
 명령줄 프로파일러 세션을 초기화하고 지정된 프로파일링 방법을 설정합니다.  
  
 **TargetCLR**  
 프로파일링 세션에 둘 이상의 .NET Framework CLR\(공용 언어 런타임\) 버전이 로드될 때 프로파일링할 버전을 지정합니다.  기본적으로는 첫 번째로 로드되는 버전이 프로파일링됩니다.  
  
 **GlobalOn GlobalOff**  
 프로파일링을 다시 시작\(**GlobalOn**\)하거나 일시 중지\(**GlobalOff**\)하지만 프로파일링 세션을 종료하지는 않습니다.  
  
 **ProcessOn:** `PID` **ProcessOff:** `PID`  
 지정된 프로세스에 대한 프로파일링을 다시 시작\(**ProcessOn**\)하거나 일시 중지 \(**ProcessOff**\)합니다.  
  
## 간격 옵션  
 다음 샘플링 간격 옵션 중 하나를 Attach 명령줄에서 지정할 수 있습니다.  기본 샘플링 간격은 10,000,000개의 프로세서 클록 주기입니다.  
  
 **Timer**\[**:**`Cycles`\]**PF**\[**:**`Events`\]**Sys**\[**:**Events\]**Counter**\[**:**`Name`,`Reload`,`FriendlyName`\]  
 샘플링 간격의 수와 형식을 지정합니다.  
  
-   **Timer** \- 프로세서 클록 주기가 `Cycles`로 지정한 개수가 될 때마다 샘플링합니다.  `Cycles`가 지정되지 않은 경우 10,000,000개의 주기가 사용됩니다.  
  
-   **PF** \- 페이지 폴트가 `Events`로 지정한 개수가 될 때마다 샘플링합니다.  `Events`가 지정되지 않은 경우 10개의 페이지 폴트가 사용됩니다.  
  
-   **Sys** \- 운영 체제에 대한 호출이 `Events`로 지정한 개수가 될 때마다 샘플링합니다.  `Events`가 지정되지 않은 경우 10개의 시스템 호출이 사용됩니다.  
  
-   **Counter** \- `Name`으로 지정한 CPU 성능 카운터가 `Reload`로 지정한 개수가 될 때마다 샘플링합니다.  필요한 경우 `FriendlyName`을 통해 프로파일러 보고서의 열 머리글로 사용할 문자열을 지정할 수 있습니다.  
  
## 예제  
 이 예제에서는 프로세스 ID가 12345인 실행 중인 응용 프로그램 인스턴스에 연결하는 방법을 보여 줍니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Attach:12345  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)