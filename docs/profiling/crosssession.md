---
title: "CrossSession | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b9fcb9c3-7903-478c-9b7c-dbd94092fcba
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# CrossSession
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPerfCmd.exe **CrossSession** 옵션을 사용하면 프로파일러가 임의의 콘솔 세션에서 데이터를 수집할 수 있습니다.  **CrossSession** 옵션은 **Start** 옵션과 함께 사용해야 합니다.  
  
 **CrossSession** 대신 약식 표현인 **CS**를 사용할 수 있습니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Start:Method /CrossSession [Options]  
```  
  
#### 매개 변수  
 없음  
  
## 유효한 옵션  
 다른 세션에서 프로파일링을 사용하려면 **Start** 옵션으로 **CrossSession** 옵션을 지정해야 합니다.  **CrossSession**은 후속 **VSPerfCmd Attach** 및 **Detach** 명령에도 지정해야 합니다.  
  
 **Start:** `Method`  
 **Start** 옵션은 프로파일러를 지정된 프로파일링 방법으로 초기화합니다.  
  
 **Attach:** *PID*\[**,***PID*\]  
 지정된 프로세스의 프로파일링을 시작합니다.  
  
 **Detach**\[**:***PID*\[,*PID*\]\]  
 지정된 프로세스의 프로파일링을 중지합니다.  
  
## 예제  
 이 예제에서는 **CrossSession** 옵션을 사용하여 다른 콘솔 세션에서 시작된 응용 프로그램에 연결합니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /CrossSession  
VSPerfCmd.exe /Attach:12345 /CS  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)