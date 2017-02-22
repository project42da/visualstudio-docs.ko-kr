---
title: "Status | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ba656fa4-ef9d-4d8c-a3b6-739c3b5d23ae
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Status
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPerfCmd.exe **Status** 옵션은 프로파일러의 상태와 현재 프로파일링 중인 프로세스에 대한 정보를 표시합니다.  
  
 **Status** 옵션은 명령줄에서 단독으로 지정해야 합니다.  상태를 표시하려면 먼저 VSPerfCmd.exe **Start** 옵션으로 프로파일러를 초기화해야 합니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Status  
```  
  
#### 매개 변수  
 없음  
  
## 설명  
 **Status** 옵션은 프로파일러에 대해 다음과 같은 상태 정보를 표시합니다.  
  
 **Output File Name**  
 현재 프로파일러 데이터 파일의 경로와 파일 이름입니다.  
  
 **Collection Mode**  
 SAMPLE 또는 TRACE  
  
 **Maximum Processes**  
 한 번에 프로파일링할 수 있는 최대 프로세스 수 및 현재 활성 상태인 프로세스 수입니다.  
  
 **Maximum Threads**  
 한 번에 프로파일링할 수 있는 최대 스레드 수입니다.  
  
 **Number of Buffers**  
 프로파일링 데이터를 쓰는 데 전용으로 할당된 메모리 바이트 수입니다.  
  
 **Size of Buffers**  
 메모리 버퍼의 크기\(바이트\)입니다.  
  
 **Status** 옵션은 현재 프로파일링 중인 각 프로세스에 대해 다음과 같은 상태 정보를 표시합니다.  
  
 **Process**  
 프로파일링되는 프로세스의 이름입니다.  
  
 **Process ID**  
 프로세스의 시스템 식별자입니다.  
  
 **Num Threads**  
 현재 실행 중인 스레드 수입니다.  
  
 **Start\/Stop Count**  
 이 프로세스의 데이터 수집을 제어하기 위한 기본 내부 프로파일러 카운트입니다.  이 카운트가 1이어야 데이터가 수집됩니다.  Start\/Stop 카운트는 프로파일러 API와 VSPerfCmd 옵션 **GlobalOn**, **GlobalOff**, **ProcessOn**, **ProcessOff**, **ThreadOn** 및 **ThreadOff**를 사용하여 조작할 수 있습니다.  
  
 **Suspend\/Resume Count**  
 이 프로세스의 데이터 수집을 제어하기 위한 보조 내부 프로파일러 카운트입니다.  이 카운트가 0보다 작거나 같아야 데이터가 수집됩니다.  **Suspend\/Resume** 카운트는 프로파일러 API를 통해서만 조작할 수 있습니다.  
  
 **Users with access rights to monitor**  
 프로파일러에 액세스할 수 있는 사용자의 이름을 나열합니다.  VSPerfCmd.exe **Admin** 옵션을 사용하여 추가 사용자에게 액세스 권한을 부여할 수 있습니다.  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)