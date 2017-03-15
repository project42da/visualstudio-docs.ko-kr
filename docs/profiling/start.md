---
title: "시작 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b85d0fe9-f67a-4b7c-8d48-7eecf3f2dfe9
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# 시작
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**Start** 옵션은 프로파일러를 지정된 프로파일링 방법으로 초기화하는 VSPerfCmd.exe 옵션입니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### 매개 변수  
 `Method`  
 다음 키워드 중 하나여야 합니다.  
  
-   **TRACE** \- 계측 방법을 지정합니다.  
  
-   **SAMPLE** \- 샘플링 방법을 지정합니다.  
  
-   **COVERAGE** \- 코드 검사를 지정합니다.  
  
-   **CONCURRENCY** \- 리소스 경합 방법을 지정 합니다.  
  
## 필수 옵션  
 명령줄에서 **Start**를 지정할 때 **Output** 옵션도 지정해야 합니다.  
  
 **Output:** `filename`  
 출력 파일 이름을 지정합니다.  
  
## 배타적 옵션  
 다음 옵션은 단일 명령줄에서 **Start** 옵션과 함께만 사용할 수 있습니다.  
  
 **CrossSession**&#124;**CS**  
 크로스 프로세스 프로파일링을 사용합니다.  옵션 이름 **CrossSession**과 **CS**가 모두 지원됩니다.  
  
 **User:**\[`domain\`\]`username`  
 지정된 계정에서 클라이언트가 모니터에 액세스할 수 있도록 합니다.  
  
 **WinCounter:** `Path` \[**Automark**:`n`\]  
 **WinCounter**는 프로파일링 데이터 파일에 표시로 포함할 Windows 성능 카운터를 지정합니다.  **AutoMark**는 데이터 파일이 수집되는 간격을 밀리초 단위로 지정합니다.  
  
## 잘못된 옵션  
 다음 옵션은 단일 명령줄에서 **Start** 옵션과 함께 사용할 수 없습니다.  
  
 **Status**  
 **Status**는 프로파일링되는 프로세스에 적용됩니다.  프로세스와 스레드 및 현재 프로파일 상태\(On\/Off\)가 나열됩니다.  예를 들어 프로세스가 중지된 경우 **Status**는 보고서에 이 상태를 표시하지 않습니다.  **Status**는 프로세스의 프로파일링 여부를 표시합니다.  
  
 **Shutdown**\[**:**`Timeout`\]  
 프로파일러를 해제합니다.  
  
## 예제  
 다음 예제에서는 VSPerfCmd.exe **Start** 옵션을 사용하여 프로파일러를 초기화하는 방법을 보여 줍니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)